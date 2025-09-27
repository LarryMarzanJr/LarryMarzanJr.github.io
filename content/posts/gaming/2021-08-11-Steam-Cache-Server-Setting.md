---
title: "Steam Cache untuk menyimpan Game hasil Download"
subtitle: ""
date: 2021-08-11T10:08:00+08:00
lastmod: 2021-08-11T10:08:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [lancache]
categories: [gaming]

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

# Latar Belakang
Mengapa Menggunakan Steam Cache?

1. Jika kita mendownload game steam yang sangat besar, kemudian reinstall kembali di kemudian hari maka membutuhkan waktu serta quota internet yang lumayan besar
2. Dengan adanya steam cache server, kita bisa mengemat waktu karena ketika download kembali game tersebut kita sudah memiliki backup tanpa harus download ulang lewat internet, melainkan secara lokal dari server kita

Dengan alasan tersebut maka kita menggunakan Steam Cache. 

# Instalasi

## Install Docker
Berikut adalah link cara instalasi docker di [Linux](https://larrymarzanjr.github.io/docker/2022/02/12/cara-install-docker-container.html) dan [Windows](https://larrymarzanjr.github.io/docker/2022/02/18/install-docker-desktop-win10-integrasi-WSL-Ubuntu.html)


## Install lancache
Install lancache:
```
sudo docker pull lancachenet/monolithic
```
Run lancache:
```bash
sudo docker run --restart unless-stopped --name lancache --detach -v /srv/pool/cache:/data/cache -v /srv/pool/cache/logs:/data/logs -p 80:80 lancachenet/monolithic:latest
```

## Install lancache-dns
Install lancache-dns:
```
sudo docker pull lancachenet/lancache-dns
```

Run lancache-dns:
```bash
sudo docker run --restart unless-stopped --name lancache-dns --detach -p 53:53/udp -e USE_GENERIC_CACHE=true -e LANCACHE_IP=192.168.x.x lancachenet/lancache-dns:latest
```

IP `192.168.x.x` adalah server kita dimana steam cache terinstall.

## Lancache log
Untuk melihat log file lancache, jalankan perintah
```bash
sudo docker exec -it lancache tail -f /data/logs/access.log
```

Sumber:

[Youtube.com - Steam Library Caching](https://www.youtube.com/watch?v=cSi-NOlomLc&t=1229s) 
