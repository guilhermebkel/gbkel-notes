# Proxy from Kubernetes Ingress Controller to URL

1. Create a deployment with [**nginx-proxy-pass-docker**](https://hub.docker.com/r/mikesplain/nginx-proxy-pass) image.

**Obs:** Use the env ```TARGET_SERVER``` to set the url you want to make the proxy to.

2. Create a **Service** of type **ClusterIP** with **Port 80** pointing at the deployment you created above.

3. Create a Ingress Controller to expose this deployment on web. The URL of this Ingress Controller will make a proxy to the target server set on the first step.


### Bibliographic References:

> https://github.com/mikesplain/nginx-proxy-pass-docker