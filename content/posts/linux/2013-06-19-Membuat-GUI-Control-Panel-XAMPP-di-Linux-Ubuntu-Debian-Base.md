---
title:  "Membuat GUI Control Panel XAMPP di Linux Ubuntu / Debian Base"
subtitle: ""
date:   2013-06-19T00:00:00+08:00
lastmod:   2013-06-19T00:00:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
#images: 'assets/images/Testing.png'

tags: [xampp]
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

![XAMPP Control Panel](http://3.bp.blogspot.com/-vfGcG58dIUM/UcEyVD0wtnI/AAAAAAAAADU/LBkpNuM0r8E/s320/xampp-control-panel-ubuntu-linux-cinnamon.jpg)

Ketika kita melakukan instalasi XAMPP di Linux Ubuntu, tidak ada GUI Panel yang dapat ditemukan untuk menjalankan atau menghentikan server dan komponen lainnya. Cara yang sering digunakan adalah dengan mengetikkan perintah pada terminal. Misalkan kita akan menjalankan server dengan perintah `sudo /opt/lampp/lampp start` sedangkan menghentikannya dengan `sudo /opt/lampp/lampp stop` .
Pada sistem operasi lainnya sudah ada GUI Control Panel untuk melakukan ini sehingga pengguna dengan mudah dapat menjalankan dan menghentikan service ini.

Namun bagi pengguna linux ubuntu dan keturunannya tidak usah kecewa, karena ada cara untuk memperoleh GUI Control panel ini dengan mudah.

Bagaimana Caranya?

Pertama kita butuh 'python-glade2' pada OS linux anda. Ketik di terminal:
```bash
sudo apt-get install python-glade2
```

Kemudian buat file baru di desktop dengan nama 'Xampp.desktop'. Ketik di terminal:
```bash
sudo gedit ~/Desktop/Xampp.desktop
```
Sesudah itu file xampp.desktop akan terbuka lewat text editor dalam keadaan kosong. Nah, di dalam text tersebut anda tambahkan kode di bawah ini.
```
[Desktop Entry]
Encoding=UTF-8
Name=Xampp Control Panel
Comment=Start or Stop XAMPP
Exec=gksudo python /opt/lampp/share/xampp-control-panel/xampp-control-panel.py
Icon=/opt/lampp/htdocs/favicon.ico
Categories=Application;Development;Web
Version=1.0
Type=Application
Terminal=0
```

Jika server Xampp anda terinstall di folder lain diluar **/opt** maka anda harus mengubah direktori pada **Exec** dan **Icon** sesuai folder anda.

Ganti file permission pada file Xampp.desktop agar file tersebut dapat dijalankan. Ketik di terminal:
```bash
sudo chmod +x ~/Desktop/Xampp.desktop
```

Nah, dengan ini anda sudah memperoleh GUI Control Panel XAMPP untuk Linux Ubuntu / Debian base.
