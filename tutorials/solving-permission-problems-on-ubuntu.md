# Solving permission problems on Ubuntu

In case you try to run a command not using *sudo* but it requires permission, avoid using *sudo*, do it instead:

```sh
sudo chown -R $YOUR_USER /folder-path-that-requires-permissions/
```

### Bibliographic References:
> https://stackoverflow.com/questions/51330217/permission-denied-home-ugurkaya-aws-credentials
