---
layout: post
title:  "Cara Mudah Menggunakan Composer"
date:   2015-10-23 10:40:14 +0800
categories: php
---

![Composer](http://3.bp.blogspot.com/-bZmpSD9gcF8/ViqwccuT-jI/AAAAAAAAFW0/ipwLVYml04o/s1600/logo-composer-transparent2.png)

Instalasi Composer di Windows tergolong super mudah karena kita hanya perlu men-download installer [Composer-Setup.exe](https://getcomposer.org/Composer-Setup.exe){:target="_blank"} dan setelah selesai download, double-click file tersebut untuk memulai proses instalasi.

Sedangkan bagi anda yang menggunakan Linux, instalasinya pun mudah. Anda hanya perlu membuka terminal shell, kemudian masuk ke direktori webserver lokal anda mis.
```
cd /var/www/html
```
Kemudian install Composer didalam direktori ini dengan mengetikkan perintah:
```
php -r "readfile('https://getcomposer.org/installer');" | php
```
Agar composer dapat digunakan di direktori mana saja ketik perintah berikut:
```
mv composer.phar /usr/local/bin/composer
```

Composer sudah siap digunakan.
Selamat mencoba!