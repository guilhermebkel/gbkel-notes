# Setting up Captain Rover

1. Create a instance on a cloud service.

2. Enable access to the following ports to that instance (on AWS you do that on the security groups): **80,443,3000,996,7946,4789,2377**.

3. Get into the instance and run the following command to enable firewall:

```sh
ufw allow 80,443,3000,996,7946,4789,2377/tcp; ufw allow 7946,4789,2377/udp;
```

4. Use the following commands to install docker:

```sh
sudo apt-get update
sudo apt-get remove docker docker-engine docker.io
sudo apt install docker.io
sudo systemctl start docker
sudo systemctl enable docker
```

5. Install Captain Rover with the following commands:

```sh
docker run -p 80:80 -p 443:443 -p 3000:3000 -v /var/run/docker.sock:/var/run/docker.sock -v /captain:/captain caprover/caprover
```

### Bibliographic References:
> https://caprover.com/docs/get-started.html