# Mengelola Versi Php di Debian 11

Seiring waktu, PHP me-release versi baru. Terkadang aplikasi yang kita buat atau gunakan
memiliki beberapa versi sehingga kita perlu berpindah versi PHP sesuai kebutuhan.

## Periksa Versi PHP anda
Untuk mengetahui versi PHP yang terinstall di komputer anda, gunakan perintah berikut:
```bash
php -v
```
Hasilnya akan muncul kurang lebih seperti dibawah ini, sesuai versi PHP yang terinstall saat
itu :
```bash
PHP 8.3.1 (cli) (built: Dec 21 2023 20:12:13) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.3.1, Copyright (c) Zend Technologies
    with Zend OPcache v8.3.1, Copyright (c), by Zend Technologies
    with Xdebug v3.3.0, Copyright (c) 2002-2023, by Derick Rethans
Add ondrej/php PPA
```

Jalankan perintah berikut untuk menambahkan repository PHP di Linux anda:
```bash
sudo add-apt-repository ppa:ondrej/php
```

## Melakukan Instalasi PHP versi lainnya
Gunakan perintah berikut untuk instalasi php:
```bash
sudo apt install php7.3
```
Ganti bagian `php7.3` dengan sesuai dengan versi PHP yang diinginkan.

## Mengaktifkan PHP versi lainnya
Jika anda ingin berpindah versi, lakukan perintah:
```bash
which php
```
Hasilnya, kita mendapatkan direktori ini:
```bash
/usr/bin/php
```
Mari kita periksa apa yang ada di dalam direktori tersebut:
```bash
ls -la /usr/bin/php
rwxrwxrwx 1 root root 21 jan  1 21:50 /usr/bin/php -> /etc/alternatives/php
```
Ternyata direktori tersebut tersambung dengan direktori lain (symlink). Kita periksa juga
direktori tersebut:
```bash
ls -la /etc/alternatives/php
lrwxrwxrwx 1 root root 15 jan  1 21:50 /etc/alternatives/php -> /usr/bin/php8.3
```
Dan lagi, kita menemukan link ke direktori lain. Kita periksa juga direktori tersebut:
```bash
ls /usr/bin/php*
/usr/bin/php  /usr/bin/php8.3 /usr/bin/php7.3
```
Dengan ini, kita sudah bisa mengetahui semua versi php yang terinstall.
Jika ingin mengganti ke PHP versi `7.3` gunakan perintah:
```bash
sudo update-alternatives --config php
```
```
There are 2 choices for the alternative php (providing /usr/bin/php).
Selection Path Priority Status

------------------------------------------------------------

* 0 /usr/bin/php8.3 83 auto mode
1 /usr/bin/php7.3 73 manual mode
2 /usr/bin/php8.3 83 manual mode

Press <enter> to keep the current choice[*], or type selection number:
```
Pilih versi yang ingin anda gunakan. Misalnya `7.3`.
Jalankan kembali perintah berikut:
```bash
php -v
```
```bash
PHP 7.3.33-14+0~20230902.114+debian11~1.gbp764b27 (cli) (built: Sep  2 2023 07:10:18) ( NTS )
Copyright (c) 1997-2018 The PHP Group
Zend Engine v3.3.33, Copyright (c) 1998-2018 Zend Technologies
    with Zend OPcache v7.3.33-14+0~20230902.114+debian11~1.gbp764b27, Copyright (c)
    1999-2018, by Zend Technologies
```

Bisa kita lihat versi php sudah berubah menjadi `7.3`.

## Referensi
[Dev.to tentang How To Update PHP in Linux to any version](https://dev.to/xxzeroxx/how-to-update-php-in-linux-to-any-version-16mp)

