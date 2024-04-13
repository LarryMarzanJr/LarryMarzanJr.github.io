---
title: "Ubah Commit Menggunakan Git Rebase"
date: 2024-03-31T14:17:47+08:00
lastmod: 2024-03-31T14:17:47+08:00
draft: false
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [git]
categories: [git]

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
## Periksa Log Hasil Commit
Untuk mengetahui perubahan atau hasil commit yang dilakukan di repository anda, lakukan perintah
```bash
git log --oneline
```
Dengan demikian kita dapat mengetahui `Sha-ID` dari setiap commit yang dilakukan seperti contoh berikut.
```bash
280f1fe make migration `create settings table`
db3e02c make migration `create sale details table`
81289eb make migration `create sales table`
```
## Rebase
Misalnya kita ingin melakukan rebase mulai dari Sha-ID `db3e02c`, maka kita perlu menggunakan Sha-ID sebelum commit tersebut, yaitu pada Sha-ID `81289eb`. Maka perintah rebase menjadi seperti berikut ini
```bash
git rebase -i 81289eb
```
Rebase bisa juga dilakukan dengan cara menghitung urutan `HEAD` dari git log. Misalnya kita ingin melakukan rebase dari commit terakhir, dalam hal ini `280f1fe`, maka bisa dengan perintah berikut
```bash
git rebase -i HEAD~1
```
> `~1` pada `HEAD~1` menunjukkan pada urutan commit ke berapa kita akan melakukan rebase, sehingga untuk melakukan urutan ke2 terakhir bisa menjadi `git rebase -i HEAD~2`

## Push Force
Setelah rebase dilakukan maka hasil commit secara lokal telah berubah. Untuk mengupdate commit dari sisi remote tentunya kita perlu melakukan git push. Dalam hal ini kita wajib menambahkan flag `--force` atau `-f` untuk dapat mengupdate commit di sisi remote.
```bash
git push --force
