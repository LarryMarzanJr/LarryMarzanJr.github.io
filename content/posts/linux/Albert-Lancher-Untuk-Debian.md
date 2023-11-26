---
title: "Albert Launcher Untuk Debian"
subtitle: ""
date: 2023-11-26T21:15:11+08:00
lastmod: 2023-11-26T21:15:11+08:00
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [debian]
categories: [package-manager, linux]

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

## Proses Install Albert Launcher di Debian 11
Untuk instalasi Albert Launcher di Debian 11,gunakan perintah berikut:
```bash
echo 'deb http://download.opensuse.org/repositories/home:/manuelschneid3r/Debian_11/ /' | sudo tee /etc/apt/sources.list.d/home:manuelschneid3r.list
curl -fsSL https://download.opensuse.org/repositories/home:manuelschneid3r/Debian_11/Release.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/home_manuelschneid3r.gpg > /dev/null
sudo apt update
sudo apt install albert
```
Albert Launcher sudah siap digunakan.

# Referensi
[albert from home:manuelschneid3r project](https://software.opensuse.org/download.html?project=home:manuelschneid3r&package=albert)
