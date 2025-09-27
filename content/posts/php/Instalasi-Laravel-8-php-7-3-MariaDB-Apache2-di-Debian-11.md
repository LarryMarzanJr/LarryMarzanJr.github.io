---
title: "Instalasi Laravel 8, PHP 7.3, MariaDB, Composer, Node.js 18 dan Apache2 Di Debian 11"
date: 2024-03-13T11:15:16+08:00
lastmod: 2024-03-13T11:15:16+08:00
draft: true
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [php, laravel, debian]
categories: [php]

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
  disqus:
    enable: true
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

Dalam menginstall Laravel 8, kebutuhan versi aplikasi yang disarankan(compatible) maupun
minimal adalah:
* `Laravel 8`
* `Php 7.3`
* `MariaDB`
* `Composer`
* `Apache2`
* `NodeJS 18`

## Install Apache2 Server:
```bash
sudo apt update
sudo apt install apache2
```

## Install & configure php7.3:
```bash
sudo apt install -y lsb-release ca-certificates curl php7.3-cli php7.3-common php7.3-mysql php7.3-zip php7.3-gd php7.3-mbstring php7.3-curl php7.3-xml php7.3-bcmath
```
enable PHP extensions
```bash
sudo nvim /etc/php/7.3/apache2/php.ini
```
Uncomment pada bagian extension untuk melakukan enable PHP extension `fileinfo`, `openssl`, dan `mbstring`.
```
extension=fileinfo
extension=mbstring
extension=openssl
```

## Install & Configure MariaDB database server
Install MariaDB:
```bash
sudo apt install mariadb-server
```
Setelah instalasi, login ke MariaDB
```bash
sudo mysql -u root -p
```
Tambahkan user untuk database, kemudian database untuk aplikasi kita:
```sql
CREATE DATABASE laravelapp;
CREATE USER laravel@localhost IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON laravelapp.* TO laravel@localhost;
FLUSH PRIVILEGES;
```

## Install composer 2.3.5:
```bash
curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version=2.3.5
composer self-update 2.3.5
```

## Install dan Konfigurasi Configure Laravel 8
Buat direktori untuk project anda, di direktori `home` user anda di Linux debian:
```bash
mkdir -p /home/$USER/{Projects/{Htdocs}}
```
Change ownership of the projects folder:
```bash
sudo chown -R www-data:www-data /home/$USER/{Projects/{Htdocs}}
```
Ubah hak akses direktori `Htdocs` menjadi `775` (rwxrwxr-x), agar user yang masuk dalam grup
`www-data` mendapatkan akses penuh pada aplikasi yang ada di dalam direktori tersebut.
```bash
sudo chmod -R 775 /home/$USER/Projects/Htdocs
```
Tambahkan user anda ke grup `www-data`:
```bash
sudo usermod -a -G www-data $USER
```
Masuk ke direktori aplikasi anda:
```bash
cd /home/$USER/Projects/Htdocs
```
Kemudian anda sudah bisa mulai membuat aplikasi laravel 8 menggunakan composer:
```bash
composer create-project laravel/laravel=8.x /home/$USER/Projects/Htdocs/testing-app --prefer-dist
```
Setelah itu, aplikasi Laravel `testing-app` sudah bisa anda akses di
`/home/$USER/Projects/Htdocs/testing-app`

## Konfigurasi Virtual Host untuk Apache2
Buat file konfigurasi untuk modul Apache2, dalam hal ini dinamakan `projects.conf` (bisa
juga dengan nama lain):
```bash
sudo nano /etc/apache2/sites-available/projects.conf
```
Tambahkan konfigurasi berikut di dalam file `projects.conf` yang anda buat:
```html
 <VirtualHost *:80>
    ServerAdmin admin@myserver.dev                                                     
    ServerName myserver.dev                                                            
    DocumentRoot /home/$USER/Projects/Htdocs                                           
  
    <Directory />
        Options FollowSymLinks
        AllowOverride None
    </Directory>
    <Directory /home/$USER/Projects/Htdocs>
        AllowOverride All
    </Directory>
 
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
 </VirtualHost>
```
> **Catatan:**
> * Ganti variabel `$USER` pada file `projects.conf`dengan nama user linux anda
> * Pada ServerAdmin, `admin@myserver.dev` dapat diganti sesua alamat email yang anda inginkan
> * Pada ServerName, `myserver.dev` akan menjadi nama dari virtual host anda, saat dipanggil
>   di browser secara lokal, akan menjadi _http://myserver.dev/_

Aktivasi modul rewrite Apache2 dan aktifkan modul `projects.conf` menggunakan perintah:
```bash
sudo a2enmod rewrite
sudo a2ensite projects.conf
```
Verifikasi konfigurasi Apache2 untuk memastikan tidak ada error:
```bash
sudo apachectl configtest
```
Restart servis `Apache2` untuk mengaktifkan konfigurasi virtual host yang kita buat untuk
project Laravel 8 kita.
Restart the Apache2 service to apply a new virtual host configuration for the Laravel project using the below command.
```bash
sudo systemctl restart apache2
```
Sekarang anda telah selesai melakukan konfigurasi virtual host untuk Laravel.

Pada komputer anda, ubah file `/etc/hosts` menggunakan text editor nano/vim/dll.
```bash
sudo nano /etc/hosts
```
Tambahkan konfigurasi di bawah ini. Pastikan nama domain sesuai dengan nama yang anda kelola
tadi, dalam hal ini `myserver.dev`, kemudian IP address sesuai dengan yang terdaftar pada
komputer anda
```
192.168.10.15 myserver.dev
```
Simpan file `/etc/hosts`, dan aplikasi `Laravel 8` yang anda bentuk sudah bisa diakses dari `http://myserver.dev/testing-app/public`

## Package Manager Node.JS
Untuk instalasi package, di `Laravel 8` menggunakan `Nodejs 18` dengan menggunakan
`npm` sebagai package manager. Untuk panduan selengkapnya klik [Instalasi Node.js dan npm Versi tertentu Menggunakan NVM
(Node Version Manager) di Debian
11](https://larrymarzanjr.github.io/instalasi-nodejs-dan-npm-menggunakan-nvm-di-debian-11/).

## Refference

[StackOverflow tentang "How To Install Specified Version of Composer"](https://stackoverflow.com/questions/51324721/how-to-install-specified-version-of-composer)

[Techdiaries.com tentang "Install Laravel 8 with PHP 7.3 & Composer"](https://www.techiediaries.com/install-laravel-8-php-7-3-composer/)

[Tutsmake tentang memperbaiki error "laravel log could not be opened"](https://www.tutsmake.com/how-to-fix-error-laravel-log-could-not-be-opened/)

[Laravel.com tentang minimum requirements Laravel 8](https://laravel.com/docs/8.x/releases)--

