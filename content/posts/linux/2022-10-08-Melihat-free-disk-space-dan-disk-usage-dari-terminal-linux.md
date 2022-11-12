---
title: "Melihat Free Disk Space dan Disk Usage Melalui Terminal atau CLI Menggunakan Perintah df"
subtitle: ""
date: 2022-10-08T06:13:00+08:00
lastmod: 2022-10-08T06:13:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [linux]
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

## Daftar Isi  
[Melihat Total, Ketersediaan dan Penggunaan Disk](#df_intro)

[Referensi](#reference)



<a name="df_intro"/>

## Melihat Total, Ketersediaan dan Penggunaan Disk

```bash
df
```

Jika ingin melihat disk usage dalam satuan megabytes, anda gunakan tag `-BM`, dalam gigabytes `-BG`. Contoh:
```bash
df -BM
```
Human readable atau dapat dibaca oleh bahasa manusia biasanya menambahkan tag `-h`
```bash
df -h
```
Untuk menampilkan angka disk dalam inodes tambahkan `-i`
```bash
df -i
```
Kita dapat mengetahui filesystem dalam disk (ext4,NTFS, dll.) dengan menambahkan tag `-T`
```bash
df -T
```
Mengecualikan filesystem tertentu (exclude)
```bash
df -x <filesystem>
```
Mengecualikan filesystem tertentu dan menambahkan total di paling bawah
```bash
df -x <filesystem> --total
```
Menampilkan disk dengan filesystem tertentu saja
```bash
df -t <filesystem>
```
Menampikan disk partisi tertentu
```bash
df /dev/sdX1
```

Dengan mengkombinasikan tag yang ada, kita bisa memperoleh informasi disk sesuai kebutuhan. Semoga bermanfaat

<a name="reference"/>

## Referensi
- [howtogeek.com tentang How to View Free Disk Space and Disk Usage From the Linux Terminal](https://www.howtogeek.com/409611/how-to-view-free-disk-space-and-disk-usage-from-the-linux-terminal/){:target="_blank"}
