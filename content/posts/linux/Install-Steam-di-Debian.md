---
title:  "Cara Install Steam di Debian"
subtitle: ""
date:   2026-05-13T09:35:00+08:00
lastmod:   2026-05-13T09:35:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [gaming]
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

## Daftar Isi  
[Memeriksa architechture Komputer](#architechture)

[Menambahkan Architechture 32 bit](#32bit)

[Enable Repository Debian](#repository)

[Install Driver GPU](#driver)

[Install Steam](#steam)

[Referensi](#refference)


<a name="architechture"/>

## Memeriksa Architechture Processor pada Komputer

Kita perlu mengetahui jenis Arsitektur processor pada komputer kita apakah 32bit atau 62bit.
Jika processor anda 32bit maka proses penambahan arsitektur 32bit pada langkah bisa di-skip
dan lanjut pada penambahan repository debian.

Cara mengetahui jenis arsitektur dengan mengetikkan:
```zsh
lscpu
```


<a name="32bit"/>

## Menambahkan Architechture 32 bit

Jika diketahui arsitektur Komputer anda adalah 64bit, maka tambahkan support untuk
arsitektur 32bit:
```zsh
sudo dpkg --add-architecture i386
sudo apt update
```


<a name="repository"/>

## Enable Repository Debian

Pastikan Repository Debian, dalam hal ini jika menggunakan Debian 13 maka jika anda periksa:
```zsh
cat /etc/apt/sources.list
```
Akan muncul seperti ini:
```zsh
deb http://deb.debian.org/debian trixie main contrib non-free non-free-firmware
deb http://security.debian.org/debian-security trixie-security main contrib non-free non-free-firmware
deb http://deb.debian.org/debian trixie-updates main contrib non-free non-free-firmware
```


<a name="driver"/>

## Install Driver GPU

Jika driver GPU Nvidia, install package support untuk driver tersebut:
```zsh
sudo apt install nvidia-driver firmware-misc-nonfree
```

Jika driver GPU AMD, install package berikut:
```zsh
sudo apt install \
mesa-vulkan-drivers \
mesa-vulkan-drivers:i386 \
libgl1-mesa-dri:i386 \
libgl1:i386 \
libgtk-3-0:i386 \
vulkan-tools
```

Untuk support GPU yang sudah sangat lama, beberapa game butuh egacy OpenGL driver. Tambahkan package:
```zsh
sudo apt install \
mesa-utils \
libgl1-mesa-dri \
libglx-mesa0 \
libglx-mesa0:i386
```

Setelah instalasi driver GPU, anda perlu restart komputer:
```zsh
sudo reboot
```

<a name="steam"/>

## Install Steam

Akhirnya install client Steam dengan menjalankan perintah:
```bash
sudo apt install steam-installer
```

<a name="reference"/>

## Referensi
- [ChatGPT - Install Steam Debian 13](https://chatgpt.com/c/6a03c6b1-b2fc-83ec-9391-8acff2a1d918)
