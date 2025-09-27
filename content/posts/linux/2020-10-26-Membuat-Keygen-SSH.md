---
title: "Cara Membuat / Generate SSH keygen"
subtitle: ""
date: 2020-10-26T04:45:00+08:00
lastmod: 2020-10-26T04:45:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [ssh]
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


## Cara Membuat / Generate SSH keygen

# Instalasi

Tentunya package ssh sudah harus terinstall di system anda:
Untuk Distro berbasis debian/ubuntu/turunannya:
```
sudo apt install openssh
```

Untuk Distro Archlinux/Manjaro/Turunannya:
```
sudo pacman -S openssh
```


# Generate keygen SSH
Setelah SSH terinstall lakukan, waktunya membuat keygen ssh untuk system kita dengan mengetikkan perintah:
```
ssh-keygen -t rsa
```

Edit file `~/.ssh/id_rsa.pub` dan akan muncul:
```
ssh-rsa BiasanyaKeySSHMunculDalamKarakterRandom

```

Proses selesai.
