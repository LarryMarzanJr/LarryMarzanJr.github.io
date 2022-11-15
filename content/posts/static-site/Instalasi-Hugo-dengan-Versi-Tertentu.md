---
title: "Instalasi Hugo Dengan Versi Tertentu"
subtitle: ""
date: 2022-11-06T21:22:03+08:00
lastmod: 2022-11-06T21:22:03+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [Hugo]
categories: [Static-Site-Generator]

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

### Persiapan Install Package Manager Homebrew
Sebelum instalasi Hugo di Linux, kita perlu menginstall package manager [Homebrew](https://brew.sh/). Ikuti perintah pada site tersebut untuk menginstall Homebrew. Masukkan perintah berikut:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Install Hugo Dengan Versi Tertentu
Katakanlah misalnya anda ingin menginstal Hugo dengan versi `0.62.0` maka perintah yang diketik adalah sebagai berikut:
```bash
brew extract --version=0.62.0
```
Kemudian lanjutkan install dengan versi Hugo yang anda inginkan
```bash
homebrew/cask brew install hugo@0.62.0
```
### Referensi
[Github tentang Install specific version of Hugo via Homebrew #2941](https://github.com/Homebrew/discussions/discussions/2941#discussioncomment-3205121)

<!--more-->
