---
title: "Cara Install Node Js Di Debian 11"
subtitle: ""
date: 2022-12-15T21:39:33+08:00
lastmod: 2022-12-15T21:39:33+08:00
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [nodejs]
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

# Persiapan Sebelum Install Node Js
Kita perlu mengupdate packages dan install _curl_
```bash
sudo apt update && sudo apt install -y curl
```

# Install Node Js Sesuai Pilihan Versi

- v14.x (Active LTS)
- v12.x (Maintenance LTS)
- v16.x (Latest Version)

> v14.x (LTS)
```bash
curl -fsSL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt install -y nodejs
```

> v12.x (LTS)
```bash
curl -fsSL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt install -y nodejs
```

> v16.x
```bash
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt install -y nodejs
```

# Referensi
[ItzGeek - How to Install Node Js and Npm On Debian 11](https://www.itzgeek.com/how-tos/linux/debian/how-to-install-node-js-and-npm-on-debian-11.html)
