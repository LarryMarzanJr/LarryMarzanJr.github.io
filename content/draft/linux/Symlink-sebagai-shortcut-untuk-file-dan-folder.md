---
title: "Symlink Sebagai 'Shortcut' Untuk File Dan Folder"
subtitle: ""
date: 2022-11-21T11:34:04+08:00
lastmod: 2022-11-21T11:34:04+08:00
draft: false
author: ""
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
## Contoh Perintah
```
ln -s /home/joenmarz/folder1/file_asli.txt file.txt
```
Setelah menjalankan perintah ini kita bisa mengakses `/home/joenmarz/folder1/file_asli.txt` dengan `file.txt`
Jika terdapat perubahan pada `file.txt` maka akan berpengaruh juga pada file aslinya.

## Cara Melepas Symlink
Sebelum melepas (remove) symlink, kita perlu mengkonfirmasi bahwa file ataupun folder
tersebut benar merupakan symlink.
```
ls -l <path-ke-symlink>
```
Menjalankan perintah ini di terminal akan menampilkan properties dari file. File symlink
ditandai dengan adanya tanda panah (->) yang mengindikasikan path dari file symlink
tersebut.

Ada dua cara melepas atau menghapus symlink.
Cara pertama dengan menggunakan perintah `unlink`
```
unlink <path-ke-symlink>
```
contohnya
```
unlink file.txt
```

Cara kedua dengan menggunakan perintah `rm`. Jika anda familiar dengan linux pasti perintah
`rm` sudah sering digunakan untuk menghapus file. Dalam hal ini menghapus symlink juga bisa
menggunakan perintah yang sama.
```
rm <path-ke-symlink>
```
contohnya
```
rm files.txt
rm nama_symlink 
```
Jika kita melakukan perintah `rm nama_symlink/` akan berakibat error, karena Linux akan
menganggap `nama_symlink/` adalah sebuah directory atau folder sehinga membutuhkan tambahan
flag r dan f. Tapi bukan itu yang ingin kita lakukan.

## Cara Menemukan dan Menghapus Symlink yang Rusak
Symlink yang rusak terjadi ketika file atau folder tujuan dari sebuah symlink telah terhapus
atau berpindah path.

Contohnya jika `file.txt` berpindah tempat dari `/home/joenmarz/` ke
`/home/joenmarz/folder1`, maka symlink yang terkoneksi ke `file.txt` menjadi rusak.
Cara menemukan symlink yang rusak dari file tersebut adalah:
```bash
find /home/joenmarz -xtype l
```
Perintah ini akan menampilkan semua symlink yang rusak yang ada pada folder joenmarz, dari
file, folder bahkan sub-folder di dalamnya.
Menambahkan flag `-delete` akan otomatis menghapus symlink yang rusak, yang ada di folder
tersebut.
```bash
find /home/joenmarz -xtype l -delete
```
