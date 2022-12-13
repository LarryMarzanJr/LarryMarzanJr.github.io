---
title: "Install Debian 11 Expert Mode"
subtitle: ""
date: 2022-12-13T09:41:03+08:00
lastmod: 2022-12-13T09:41:03+08:00
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

## Minimum Requirements untuk instalasi Debian 11

| Requirements | Minimum | Rekomendasi |
| ------------ | ------- | ----------- |
| RAM          | 512MB   | 2GB         |
| Processor    | 1Ghz    |             |
| Hard Drive   | 10GB    |             |

Dengan spesifikasi komputer diatas anda sudah bisa running Debian 11 secara minimal.

## Persiapan Installer
Download image Debian 11 dari link resmi. Tergantung arsitektur komputer yang kita miliki,
apakah 32-bit atau 64-bit, pilihlah antara kedua jenis installer berikut:
Arsitektur 64 bit:
[firmware-11.3.0-amd64-netinst.iso](https://cdimage.debian.org/cdimage/unofficial/non-free/cd-including-firmware/current/amd64/iso-cd/)
Arsitektur 32 bit:
[firmware-11.5.0-i386-netinst.iso](https://cdimage.debian.org/cdimage/unofficial/non-free/cd-including-firmware/current/i386/iso-cd/)

Install file ISO yang telah didownload ke dalam USB flashdisk menggunakan
[Etcher](https://www.balena.io/etcher/) atau dengan perintah
[dd](https://larrymarzanjr.github.io/2022-01-30-membuat-linux-bootable-usb-drive-menggunakan-dd/).

## Proses Instalasi
Setelah selesai membuat installer di USB, lanjut dengan boot komputer menggunakan USB yang
telah kita buat sebagai Installer Debian 11.

Setelah masuk menu Boot, pilih **"Advanced Options"**

Pilih **Expert Install**

Pliih bahasa

Pilih lokasi untuk menentukan timezone anda

Locale berfungsi untuk menentukan format waktu, currency, ukuran kertas secara default dll.
Secara default yang terpilih adalah **en_US.UTF-8**

Pilih layout keyboard. Saya menggunakan default yaitu **American English**.

Deteksi media USB yang digunakan untuk menginstall.

Komponen instalasi terdeteksi dari media USB tersebut.

Komponen opsional dapat dipilih dari sini jika dibutuhkan.

Deteksi hardware jaringan anda di **Detect Network Hardware**

Konfigurasi jaringan pada menu **Configure the Network**. Pilih **Yes** untuk setingan DHCP
otomatis, atau pilih **No** jika anda ingin menentukan sendiri IP address secara static.

Tunggu 3 detik untuk mendeteksi link network.

Tentukan **hostname** untuk komputer anda.

Tentukan nama **domain** untuk server.

**Set up users and passwords** untuk membuat user ID pengguna.

**Enable Shadow Passwords** untuk mengenkripsi password user kita.

```
to be continued..
```

## Referensi
[dev.to tentang How To Install Debian 11 Bullseye Expert Mode Minimal Install](https://dev.to/brandonwallace/how-to-install-debian-11-bullseye-expert-mode-minimal-install-10pd)
