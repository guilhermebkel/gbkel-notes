# Debugging NodeJS inside K8s

1. Find the pod you want to debug

```sh
kubectl get pods | grep my-awesome-api 
```

2. Give a look at the process PIDs inside this pod

*Obs: You have to get the PID from the NodeJS process, it is usually 1.*

```sh
kubectl exec -it my-awesome-api  -- /bin/sh -c "ps aux"
```

3. Enable devtool in the application

```sh
kubectl exec -it my-awesome-api -- /bin/sh -c "kill -USR1 1"
```

4. Forward debug port to your computer

```sh
kubectl port-forward my-awesome-api 9229:9229
```

Now you just have to open your browser and click on the debug icon on devtools page.

### Bibliographic References:
> https://medium.com/@amirilovic/how-to-debug-node-js-applications-in-kubernetes-c169f1e88c37
