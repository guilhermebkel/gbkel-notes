# Creating an AWS EC2 with Terraform

1. Create the following Terraform file:

	```tf
	variable "bucket_name" {
		description = "Nome do bucket S3 para armazenar a chave"
		type        = string
	}

	variable "ssh_key_name" {
		description = "Nome do arquivo .pem para armazenar no S3"
		type        = string
	}

	variable "instance_name" {
		description = "Nome para a EC2"
		type        = string
	}

	provider "aws" {
		region = "us-east-1"
	}

	resource "aws_s3_bucket" "key_bucket" {
		bucket = var.bucket_name
	}

	resource "tls_private_key" "ssh_key" {
		algorithm = "RSA"
		rsa_bits  = 2048
	}

	resource "aws_s3_object" "key_file" {
		bucket  = aws_s3_bucket.key_bucket.id
		key     = var.ssh_key_name
		content = tls_private_key.ssh_key.private_key_pem
	}

	resource "aws_key_pair" "ec2_key" {
		key_name   = "ec2_ssh_key"
		public_key = tls_private_key.ssh_key.public_key_openssh
	}

	resource "aws_security_group" "web_sg" {
		name        = "web_sg"
		description = "Allow SSH, HTTP and HTTPS"

		ingress {
			from_port   = 22
			to_port     = 22
			protocol    = "tcp"
			cidr_blocks = ["0.0.0.0/0"]
		}

		ingress {
			from_port   = 80
			to_port     = 80
			protocol    = "tcp"
			cidr_blocks = ["0.0.0.0/0"]
		}

		ingress {
			from_port   = 443
			to_port     = 443
			protocol    = "tcp"
			cidr_blocks = ["0.0.0.0/0"]
		}

		egress {
			from_port       = 0
			to_port         = 0
			protocol        = "-1"
			cidr_blocks     = ["0.0.0.0/0"]
		}
	}

	resource "aws_instance" "web_server" {
		ami           = "ami-04b70fa74e45c3917"
		instance_type = "t2.micro"
		key_name      = aws_key_pair.ec2_key.key_name
		vpc_security_group_ids = [aws_security_group.web_sg.id]

		tags = {
			Name = var.instance_name
		}

		root_block_device {
			volume_type = "gp3"
			volume_size = 30
		}
	}

	resource "aws_eip" "web_ip" {
		instance = aws_instance.web_server.id
	}
	```

2. Create the following BashScript file:
	```sh
		#!/bin/bash
		export AWS_ACCESS_KEY_ID="ACESS_KEY_ID"
		export AWS_SECRET_ACCESS_KEY="SECRET_ACCESS_KEY"
		export AWS_REGION="us-east-1"

		BUCKET="guilhermebkelaws01-credentials2"
		KEY_NAME="apps.pem"
		INSTANCE_NAME="apps"

		export TF_VAR_bucket_name=$BUCKET
		export TF_VAR_ssh_key_name=$KEY_NAME
		export TF_VAR_instance_name=$INSTANCE_NAME

		# 1. Use terraform to create EC2 instance
		terraform init
		terraform apply -auto-approve

		# 2. Get the key
		aws s3 cp s3://$BUCKET/$KEY_NAME ./
		chmod 600 $KEY_NAME

		# 3. Get the EC2 public IP
		EC2_IP=$(aws ec2 describe-instances \
				--filters "Name=tag:Name,Values=$INSTANCE_NAME" \
				--query "Reservations[*].Instances[*].PublicIpAddress" \
				--output text)

		# 4. Connect to EC2
		ssh -o StrictHostKeyChecking=no -i $KEY_NAME ubuntu@$EC2_IP
	```

3. Run the bash script.
