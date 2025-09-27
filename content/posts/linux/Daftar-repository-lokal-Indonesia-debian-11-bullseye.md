---
title: "Daftar Repository Lokal Indonesia Debian 11 Bullseye"
subtitle: ""
date: 2022-11-23T07:12:46+08:00
lastmod: 2022-11-23T07:12:46+08:00
draft: false
author: ""
authorLink: ""
description: ""
license: ""
images: []

tags: [debian]
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
## Daftar Repository Lokal Indonesia Debian 11 Bullseye

Daftar Repository Lokal Indonesia Debian 11 Bullseye ada beragam, silahkan pilih sesuai
lokasi anda, mana yang lebih cepat. Selalu ingat bahwa lokasi bukanlah segalanya, kadang
walaupun secara geografis letaknya lebih dekat, belum tentu repository tersebut cocok buat
anda. Untuk itu silahkan bereksperimen mencoba masing-masing repo di bawah ini agar anda
mendapat kwalitas download package yang tercepat.

### Data Utama Surabaya
```
# Data Utama Surabaya - Indonesia
deb http://kartolo.sby.datautama.net.id/debian/ bullseye main contrib non-free
deb http://kartolo.sby.datautama.net.id/debian/ bullseye-updates main contrib non-free
deb http://kartolo.sby.datautama.net.id/debian-security/ bullseye-security main contrib non-free
```

### Kambing UI
```
# Kambing UI - Indonesia
deb http://kambing.ui.ac.id/debian/ bullseye main contrib non-free
deb http://kambing.ui.ac.id/debian/ bullseye-updates main contrib non-free
deb http://kambing.ui.ac.id/debian-security/ bullseye-security main contrib non-free 
```

### Kebo VLSM
```
# Kebo VLSM - Indonesia
deb http://kebo.vlsm.org/debian/ bullseye main contrib non-free
deb http://kebo.vlsm.org/debian/ bullseye-updates main contrib non-free
deb http://kebo.vlsm.org/debian-security/ bullseye-security main contrib non-free 
```

### Mirror Unej
```
# Mirror Unej - Indonesia
deb http://mirror.unej.ac.id/debian/ bullseye main contrib non-free
deb http://mirror.unej.ac.id/debian/bullseye-updates main contrib non-free
deb http://mirror.unej.ac.id/debian-security/ bullseye-security main contrib non-free
```

## Cara Menggunakan atau Mengganti Repository
Penggunaan atau penggantian repository berdasarkan daftar di atas sangat mudah. Silahkan
edit file `source.list` menggunakan text editor anda. Untuk mengedit file tersebut
membutuhkan hak akses setara admin, sehingga saat membukanya perlu menambahkan `sudo` untuk
memanggil file. Berikut contoh membuka file dengan beragam text editor:
### buka dengan vim
```bash
sudo vim /etc/apt/source.list
```

### buka dengan nano
```bash
sudo nano /etc/apt/source.list
```

### buka dengan vscode
```bash
sudo code /etc/apt/source.list
```

Copy dan paste repository pilihan anda pada file `source.list` tersebut, dan simpan
perubahan. Setelah ini, saat kita melakukan `apt update`, `apt upgrade`,
`apt install <package>` maka package yang didownload akan menggunakan source repository 
yang anda ubah dari `source.list`.

