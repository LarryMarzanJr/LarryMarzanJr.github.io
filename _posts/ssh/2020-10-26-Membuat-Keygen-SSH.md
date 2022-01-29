---
layout: post
title:  "Cara Membuat / Generate SSH keygen"
date:   2020-10-25 04:45:00 +0800
categories: [post, ssh]
---

## Cara Membuat / Generate SSH keygen

# Instalasi

Tentunya package ssh sudah harus terinstall di system anda:
Untuk Distro berbasis debian/ubuntu/turunannya:
```
sudo apt install openssh
```

Untuk Distro Archlinux/Manjaro/Turunannya:
```
sudo pacman -S openssh
```


# Generate keygen SSH
Setelah SSH terinstall lakukan, waktunya membuat keygen ssh untuk system kita dengan mengetikkan perintah:
```
ssh-keygen -t rsa
```

Edit file `~/.ssh/id_rsa.pub` dan akan muncul:
```
ssh-rsa BiasanyaKeySSHMunculDalamKarakterRandom

```

Proses selesai.