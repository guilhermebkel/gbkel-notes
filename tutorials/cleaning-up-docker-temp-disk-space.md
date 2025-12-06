# Cleaning Up Ubuntu Temp Disk Space

### Command

```sh
sudo docker builder prune -a -f
sudo rm -rf ~/.cache/*
sudo rm -rf ~/.sonarlint/*
sudo journalctl --vacuum-size=500M
```
