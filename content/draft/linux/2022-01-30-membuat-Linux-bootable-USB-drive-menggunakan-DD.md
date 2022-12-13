---
title:  "Membuat Linux bootable USB drive menggunakan DD"
subtitle: ""
date:   2022-01-30T17:31:00+08:00
lastmod:   2022-01-30T17:31:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [dd]
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

# Membuat Linux bootable USB drive menggunakan DD

dd adalah aplikasi/perintah paling sederhana pada linux yang digunakan dalam menyalin image ISO kedalam USB Flashdisk.

Dengan menggunakan dd anda dapat membuat bootable USB Linux sistem dengan menyalin image kedalam USB drive.

Anda dapat membuat bootable USB untuk ArchLinux, Manjaro, Ubuntu, Linux Mint, dan berbagai varian linux lainnya.

Anda juga dapat mencoba pendekatan ini dalam mambuat bootable Windows USB, jika anda menyalin image ISO Windows ke dalam USB drive.

Berikut adalah langkah-langkahnya:

### Menyalin ISO ke dalam USB flash drive
Jalankan perintah:
```bash
sudo dd bs=4M if=/path/to/iso of=/dev/sdX status=progress && sync
```

Ganti /dev/sdX dengan nama device USB anda.
Untuk mengetahui mana device USB anda, dapat dicek dengan perintah:
```
sudo fdisk -l
```

### Mengembalikan / Restore USB flash drive ke kondisi semula

##### Bersihkan flash drive anda:
```bash
sudo wipefs --all /dev/sdX
```

##### Buat partisi baru:
```bash
sudo cfdisk /dev/sdX
```
Pada saat muncul `Select Label type` pilih dos. Setelah itu write perubahan anda.

##### Format partisi menjadi FAT file system:
```bash
sudo mkfs.vfat -n 'label-USB-anda' /dev/sdX1
```
