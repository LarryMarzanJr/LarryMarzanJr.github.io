---
categories: linux
date: "2021-08-22T14:28:00Z"
title: Konfigurasi Server FTP pada Debian 10 Buster
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