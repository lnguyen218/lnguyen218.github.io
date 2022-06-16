---
title: Update Pacman archlinux-keyring
date: 2022-09-09 22:00:00 -500
categories: [readme]
tags: [linux,pacman]
---
Issues updating archlinux-keyring using the following command:
```shell
sudo pacman-key -Syu archlinux-keyring
```

Required to reinstall archlinux-keyring. First remove existing key:
```shell
sudo rm -rf /etc/pacman.d/gnupg
```

Then populate from archlinux
```shell
sudo pacman-key --populate archlinux
```

---
### Outstanding issue

```shell
error: cannot remove file '/usr/': Read-only file system
```
