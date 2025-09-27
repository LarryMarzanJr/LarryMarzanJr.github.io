---
title: "Menyimpan PAT Menggunakan Git Credentials"
subtitle: ""
date: 2022-12-24T13:55:17+08:00
lastmod: 2022-12-24T13:55:17+08:00
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

# Apa itu Git Credentials?
Git credentials berfungsi untuk menyimpan data user dan email bahkan PAT (Personal Access
Token) kedalam cache secara lokal dalam PC kita. Hal ini sangat berfungsi pada saat
kita melakukan aktivitas mengedit repository (git add, git push, dsb.) agar kita tidak
menginput username maupun PAT secara berulang.

# Cara Menambahkan Git Credentials
Kita perlu membuat file yang akan digunakan sebagai sarana penyimpanan cache, misalnya
`~/.my-credentials`. Untuk mengaktifkan git credentials jalankan perintah berikut:
```bash
git config --global credential.helper 'store --file ~/.my-credentials'
```

Ada banyak cara untuk menyimpan cache credentials git anda. Salah satunya yaitu menggunakan
cara diatas. Untuk cara lainnya bisa anda dapatkan melalui situs resmi
[git-scm.com](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage).

# Referensi
[git-scm.com - Git Tools Credential Storage](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage)
