---
title: "Reset Git Repositori Lokal Mengikuti Repositori Remote"
subtitle: ""
date: 2020-09-23T18:56:00+08:00
lastmod: 2020-09-23T18:56:00+08:00
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

<!-- Sumber: -->
<!-- https://stackoverflow.com/questions/1628088/reset-local-repository-branch-to-be-just-like-remote-repository-head -->

# Restore Repositori
Katakanlah anda "blunder" pada mengedit repositori lokal dan ingin meresetnya sesuai Repositori yang tersimpan terakhir di Web anda. Lakukan perintah ini:
```bash
git fetch origin
git reset --hard origin/main
```
# Backup Repositori
Sebaliknya, katakanlah repositori lokal saat ini ingin anda simpan sementara, atau belum live, maka simpanlah di branch tersendiri sebagai backup. Lakukan perintah ini:
```
git commit -a -m "komentar anda"
git branch <nama_branch_baru>
git push origin <nama_branch_baru>
```

Sehingga contohnya menjadi seperti ini:
```
git commit -a -m "Simpan Pekerjaan saya, untuk jaga-jaga"
git branch simpan-kerjaan
git push origin simpan-kerjaan
```
