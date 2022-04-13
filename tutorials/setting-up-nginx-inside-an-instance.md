# Setting up Nginx inside an instance

**Obs:** Make sure your instance enabled access for the following ports: **80, 443, 8000, 22**.

### Giving initial access on firewall
- Basic configuration
```sh
sudo ufw allow 80,443,8000,22/tcp
sudo ufw enable
```

### Installing Docker
- Packages installation
```sh
sudo apt-get update
sudo apt-get remove docker docker-engine docker.io
sudo apt install docker.io
```

- Service initialization
```sh
sudo systemctl start docker
sudo systemctl enable docker
```

### Installing Nginx
- Packages installation
```sh
sudo apt update
sudo apt install nginx
```

- Adding a new rule to firewall
```sh
sudo ufw allow 'Nginx HTTP'
```

- Creating a blank configuration file
```sh
sudo nano /etc/nginx/conf.d/app.conf
```

- Add **client_max_body_size 16M;** on the end of **http** block of nginx main configuration file.

```sh
sudo nano /etc/nginx/nginx.conf
```

### Creating basic HTTP config

- Adding a new configuration file for nginx
```sh
sudo nano /etc/nginx/conf.d/app.conf
```

- Adding the following informations on the file created above

```nginx
server {
	listen 80;
	listen [::]:80;

	server_name your_domain.com.br;

	location / {
		proxy_pass http://localhost:9090;
	}
}
```

### Adding SSL Certificates generation

- Installing Certbot
```sh
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install python-certbot-nginx
```

- Giving access on firewall for Nginx HTTPS
```sh
sudo ufw allow 'Nginx Full'
```

- Rebooting Nginx
```sh
sudo systemctl restart nginx
```

### Adding HTTPS with Let's Encrypt SSL Certificate on Nginx

- Generating a SSL Certificate
```sh
# Make sure that the domain below is pointing at the instance IP.

sudo certbot --nginx -d your_domain.com.br

# Avoid using forced redirect from HTTP to HTTPS since it can cause some unexpected bugs.
# After creating the certificate with success, the HTTPS will start working.
```

- Rebooting Nginx
```sh
sudo systemctl restart nginx
```

### Bibliographic References:

> https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-18-04
> https://www.digitalocean.com/community/tutorials/how-to-set-up-let-s-encrypt-with-nginx-server-blocks-on-ubuntu-16-04
