---
title:  "Konfigurasi Server FTP pada Debian 10 Buster"
subtitle: ""
date:   2021-08-22T14:28:00+08:00
lastmod:   2021-08-22T14:28:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [ftp]
categories: [linux]

featuredImage: ""
featuredImagePreview: ""

hiddenFromHomePage: false
hiddenFromSearch: false
twemoji: false
lightgallery: true
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

toc:
  enable: true
  auto: true
code:
  copy: true
  maxShownLines: 50
math:
  enable: false
  # ...
mapbox:
  # ...
share:
  enable: true
  # ...
comment:
  enable: true
  # ...
library:
  css:
    # someCSS = "some.css"
    # located in "assets/"
    # Or
    # someCSS = "https://cdn.example.com/some.css"
  js:
    # someJS = "some.js"
    # located in "assets/"
    # Or
    # someJS = "https://cdn.example.com/some.js"
seo:
  images: []
  # ...
---

## Konfigurasi Server FTP pada Debian 10
Kita perlu menggunakan root akses untuk melakukan ini, atau untuk lebih aman kita menggunakan `sudo`.

# 1. Upgrade sistem Debian
Selalu lakukan update sistem terlebih dahulu, sebelum melakukan instalasi pada Distro Debian.

```bash
sudo apt update && sudo apt upgrade
```
Dengan begini, keamanan dan file yang diperlukan telah dipenuhi sebelum masuk ke pokok instalasi yaitu FTP server.

# 2. Instalasi VSFTPD di Debian 10
Sekarang kita akan menginstal daemon (service) FTP, dalam hal ini kita menggunakan VSFTPD. Penggunaannya sangat mudah dan sudah tersedia di repository Debian 10.

```bash
sudo apt install vsftpd
```
kemudian, periksa status servce vsftpd:

```bash
sudo systemctl status vsftpd
...
Active: active (running)
...
```
Artinya service FTP ini sudah berjalan.

# 3. Konfigurasi server FTP
Konfigurasi VSFTPD dapat ditemukan di `/etc/vsftpd.conf`. Sebelum mengubah file konfigurasi ini, ada baiknya kita backup dulu agar jika terjadi sesuatu diluar dugaan, kita bisa melakukan restorasi melalui file asli `vsftpd.conf`.

```bash
sudo cp /etc/vsftpd.conf /etc/vsftpd.conf.bak
```
Sekarang bisa kita lanjutkan konfigurasinya:

```bash
sudo nano /etc/vsftpd.conf
```

Disable anonymous:
```
anonymous_enable=NO
```

Nonaktifkan IPV6 jika anda tidak menggunakannya:
```
listen=YES
#listen_ipv6=NO
```
Agar bisa mengubah folder dan file pada server, kita perlu mengaktifkan `write_enable` dan `local_enable`:
```
local_enable=YES
write_enable=YES
```
Port default yang digunakan adalah 20, namun anda bisa mengubahnya:
```
#connect_from_port_20=YES
listen_port=21
```
Kita bisa mengatur pengguna yang berhak mengubah file pada server FTP dengan menyediakan file yang berisi list user. File tersebut bisa kita simpan misalnya di file `/etc/vsftpd.chroot_list`, yang bisa kita panggil melalui konfigurasi `chroot_list_file`. Kemudian aktifkan konfigurasi ini:
```
chroot_local_user=YES
chroot_list_enable=YES
chroot_list_file=/etc/vsftpd.chroot_list
```
Untuk membuat list user pada file `vsftpd.chroot_list`, lakukan langkah berikut:

```bash
sudo nano /etc/vsftpd.chroot_list
```
Kemudian di dalamnya tambahkan user, misalnya
```
joenmarz
testing1
```
Pada akhirnya konfigurasi anda akan terlihat seperti ini:

```bash
sudo cat /etc/vsftpd.conf | grep -v "^#"
```
```
listen=YES
anonymous_enable=NO
local_enable=YES
write_enable=YES
dirmessage_enable=YES
use_localtime=YES
xferlog_enable=YES
listen_port=21
chroot_local_user=YES
chroot_list_enable=YES
chroot_list_file=/etc/vsftpd.chroot_list
secure_chroot_dir=/var/run/vsftpd/empty
pam_service_name=vsftpd
```

Kemudian buat user baru:

```bash
sudo adduser testing1
```
Kemudian, restart service VSFTPD.

```bash
sudo systemctl restart vsftpd
```
Periksa kembali status service VSFTPD:

```bash
sudo systemctl status vsftpd
...
Active: active (running)
...
```

Selanjutnya, anda sudah bisa menggunakan server FTP ini dengan menginstall FTP Client pada komputer pribadi anda, atau laptop dan bisa mengakses server FTP ini.
