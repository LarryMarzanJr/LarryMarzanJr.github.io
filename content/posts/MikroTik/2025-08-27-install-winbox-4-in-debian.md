---
title: "Rekap Instalasi WinBox 4 Linux Native (Debian/Ubuntu)"

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

# Rekap Instalasi WinBox 4 Linux Native (Debian/Ubuntu)

## 1. Download dan Ekstrak
```bash
cd ~/Downloads
unzip WinBox_Linux.zip -d WinBox_Linux
cd WinBox_Linux
chmod +x WinBox
```
## 2. Jalankan WinBox
```bash
./WinBox
```

Jika muncul error terkait library yang hilang, install paket berikut satu per satu:
## 3. Paket-paket Library yang Diperlukan
|Error Library yang Muncul|	Paket yang Harus Diinstall|	Perintah Install|
|-------------------------|---------------------------|----------------|
|libxcb-icccm.so.4	      |libxcb-icccm4	          |`sudo apt install libxcb-icccm4`|
|libxcb-image.so.0	      |libxcb-image0	          |`sudo apt install libxcb-image0`|
|libxcb-keysyms.so.1	  |libxcb-keysyms1	          |`sudo apt install libxcb-keysyms1`|
|libxcb-render-util.so.0  |libxcb-render-util0	      |`sudo apt install libxcb-render-util0`|
|libxcb-shape.so.0	      |libxcb-shape0	          |`sudo apt install libxcb-shape0`|
|libxcb-xfixes.so.0	      |libxcb-xfixes0	          |`sudo apt install libxcb-xfixes0`|
|libxcb-sync.so.1	      |libxcb-sync1	              |`sudo apt install libxcb-sync1`|

>Catatan: Error biasanya muncul bertahap, jadi install paket sesuai error yang muncul satu per satu.

## 4. Jalankan Kembali

Setelah semua library terinstall:
```bash
./WinBox
```

WinBox seharusnya sudah berjalan normal tanpa error.
>Opsional: Script Instalasi Otomatis

Jika ingin, kamu bisa buat skrip bash untuk install semua paket sekaligus:
```bash
sudo apt update
sudo apt install -y libxcb-icccm4 libxcb-image0 libxcb-keysyms1 libxcb-render-util0 libxcb-shape0 libxcb-xfixes0 libxcb-sync1
```

Semoga membantu! 
