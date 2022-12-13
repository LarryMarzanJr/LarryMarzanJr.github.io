---
title:  "Cara Mudah Menggunakan Composer"
subtitle: ""
date: 2015-10-23T10:40:14+08:00
lastmod: 2015-10-23T10:40:14+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [composer]
categories: [package-manager]

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

![Composer](http://3.bp.blogspot.com/-bZmpSD9gcF8/ViqwccuT-jI/AAAAAAAAFW0/ipwLVYml04o/s1600/logo-composer-transparent2.png)

Instalasi Composer di Windows tergolong super mudah karena kita hanya perlu men-download installer [Composer-Setup.exe](https://getcomposer.org/Composer-Setup.exe) dan setelah selesai download, double-click file tersebut untuk memulai proses instalasi.

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
