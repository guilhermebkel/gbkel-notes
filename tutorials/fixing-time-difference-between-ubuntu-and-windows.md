# Fixing time difference between Ubuntu and Windows

1. Run the following command on your Ubuntu:
```sh
timedatectl set-local-rtc 1 --adjust-system-clock
```

### Bibliographic References:

> https://www.edivaldobrito.com.br/como-corrigir-diferencas-de-tempo-entre-o-ubuntu-e-o-windows-em-sistema-com-dual-boot/