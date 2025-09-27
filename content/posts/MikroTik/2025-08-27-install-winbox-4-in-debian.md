---
title: "Instalasi WinBox 4 Linux Native (Debian/Ubuntu)"

subtitle: ""
date: 2025-08-27T16:40:00+08:00
lastmod: 2025-08-27T16:40:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [mikrotik]
categories: [mikrotik]

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

# Instalasi WinBox 4 di Linux Native (Debian/Ubuntu)

## 1. Download Winbox 4 for Linux
Download dari situs resmi MikroTik:
```bash
wget https://download.mikrotik.com/routeros/winbox/4.0beta30/WinBox_Linux.zip
```
## 2. Extract File dan Buat Executable
```bash
unzip WinBox_Linux.zip -d WinBox_Linux
cd WinBox_Linux
chmod +x WinBox
```

## 3. Install pre-requisite paket
```bash
sudo apt update
sudo apt install -y libxcb-icccm4 libxcb-image0 libxcb-keysyms1 libxcb-render-util0 libxcb-shape0 libxcb-xfixes0 libxcb-sync1
```

## 4. Jalankan WinBox
```bash
./WinBox
```

WinBox seharusnya sudah berjalan normal tanpa error.

Semoga membantu! 
