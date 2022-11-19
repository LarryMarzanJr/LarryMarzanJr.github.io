---
title: "Instalasi Linux lewat WSL"
subtitle: ""
date: 2022-02-15T20:15:00+08:00
lastmod: 2022-02-15T20:15:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: [] 

tags: [WSL]
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

### Install WSL
Langkah pertama: Enable Developer Mode
The first thing you need to do is enable developer mode on your Windows machine.

Go to `Settings -> Update and Security -> For developers`,kemudian klik `Developer mode`

Selanjutnya Install WSL. Masuk ke menu Start dan cari `turn windows features on or off`. Select that, then check the “Windows Subsystem for Linux (Beta)” checkbox.

### Install Linux lewat WSL
Untuk mengetahui list disribution Linux yang tersedia secara online, buka aplikasi `Powershell` kemudian ketikkan:
```
wsl --list --online
```
![Powershell](https://www.ntweekly.com/wp-content/uploads/2021/09/image-3-1024x387.png "Powershell")
Misalnya kita memilih distro Ubuntu untuk diinstal, maka ketikkan:
```
wsl --install -d Ubuntu
```

## Referensi
- [Microsoft tentang Install WSL](https://docs.microsoft.com/en-us/windows/wsl/install){:target="_blank"}
- [wsl-guide.kennethreitz.org tentang Installing WSL](https://wsl-guide.kennethreitz.org/en/latest/installation.html){:target="_blank"}
- [ntweekly.com tentang Install WSL distribution using Command](https://www.ntweekly.com/2021/09/10/list-available-for-install-wsl-distribution-using-command/){:target="_blank"}


