# Installing NVIDIA Graphics Drivers On Ubuntu

1. To start clean, you can purge all configs you tried to install so far:

```sh
sudo apt purge '^.*nvidia*'
sudo apt install ubuntu-desktop
sudo apt purge "^.*cublas*"
sudo apt purge "^.*cuda*"
sudo mv /etc/X11/xorg.conf /etc/X11/xorg.conf.old
sudo apt autoremove
```

2. Reboot, and disable `SecureBoot` in the bios. That's extremely important, otherwise the drivers won't load

3. After SecureBoot is disabled, then you run the following commands:

```sh
sudo ubuntu-drivers devices
sudo ubuntu-drivers autoinstall
reboot
```
4. Once you reboot, you can verify that your drivers are working by issuing:

```sh
nvidia-smi
```