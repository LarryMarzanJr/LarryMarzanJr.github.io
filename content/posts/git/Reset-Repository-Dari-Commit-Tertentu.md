---
title: "Reset Repository Menggunakan Commit Tertentu"
date: 2024-03-11T15:59:52+08:00
lastmod: 2024-03-18T10:29:02+08:00
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

## Clone Repository
Lakukan Clone Repository seperti biasa
```bash
git clone <nama-repository>
```

## Melihat Commit lewat Git Log
Untuk menentukan commit yang akan kita gunakan, kita perlu mengidentifikasi Sha ID dari commit
yang akan kita gunakan dari project. Lakukan perintah
```bash
git log --oneline
```

## Checkout dari Commit Tertentu
Setelah mengetahui Sha-ID untuk commit yang rencananya akan kita gunakan, lakukan checkout
```bash
git checkout <Sha-ID>
```

## Bersihkan File Local yang tidak digunakan (Untracked Files)
Setelah checkout dari commit tertentu, biasanya terdapat file atau folder yang seharusnya
tidak ada di commit yang kita checkout, atau biasa disebut `untracked files`. Munculnya file ini karena kita melakukan clone
repository dari commit terbaru. Untuk mengetahui Untracked files tersebut, lakukan perintah
```bash
git clean -n -d
```
Untuk menghapus untracked files, lakukan perintah `git clean` dengan menambahkan flag `-f`
untuk menghapus file dan flag `-d` untuk menghapus folder/direktori.
```bash
git clean -fd
```

## Reset Repository dan Push Force
> **PERHATIAN** Dalam menjalankan reset repository dengan `git reset --hard`, perlu diketahui bahwa perubahan yang
> dilakukan setelah commit yang kita checkout atau _commit tebaru_ **AKAN IKUT TERHAPUS DI
> REPOSITORY YANG TELAH KITA UPLOAD**, setelah dilakukan `git push --force`. Untuk itu pastikan melakukan **backup terhadap file
> local sebelum menjalankan perintah reset**.

Untuk melakukan reset HEAD dari repository, lakukan perintah
```bash
git reset --hard <Sha-ID>
```

Lalu lakukan push force. Perlu diingat, setelah push force ini, maka semua commit yang
dilakukan **setelah `Sha-ID` yang kita gunakan saat ini akan terhapus dari Repository
Github**.
```bash
git push --force
```

## Referensi
[Opensource.com tentang git reset revert rebase commands](https://opensource.com/article/18/6/git-reset-revert-rebase-commands)

[Devopscube.com tentang checkout clone specific git commit id sha](https://devopscube.com/checkout-clone-specific-git-commit-id-sha/)

[Stackoverflow tentang How to remove untracked files from current
git](https://stackoverflow.com/questions/61212/how-do-i-remove-local-untracked-files-from-the-current-git-working-tree)

[Stackoverflow tentang How do I delete a commit from a branch](https://stackoverflow.com/questions/1338728/how-do-i-delete-a-commit-from-a-branch)
