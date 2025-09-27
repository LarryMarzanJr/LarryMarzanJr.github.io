---
title:  "Install Qbittorrent-Nox dan Servicenya"
subtitle: ""
date:   2022-10-28T19:20:00+08:00
lastmod:  2022-10-28T19:20:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: [] 

tags: [qbitorrent-nox]
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
## Proses Instalasi

Proses instalasi pada debian based cukup mudah:
```bash
sudo apt update
sudo apt install qbittorrent-nox
```

## Menambahkan Service qBittorrent-nox

Agar qBittorrent-nox bisa running otomatis atau secara headless, kita perlu menambahkan servicenya dengan cara membuat file `/etc/systemd/system/qbittorrent-nox.service`
Di dalam file tersebut kita input sebagai berikut
```bash
[Unit]
Description=qbittorrent-nox terminal application
After=network.target

[Service]
Type=forking
User=qbittorrent-nox
Group=qbittorrent-nox
Umask=007
ExecStart=/usr/bin/qbittorrent-nox -d --webui-port=6969
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

Tambahkan User dan Group pada system, dengan mengetikkan pada terminal
```bash
sudo adduser --system --group qbittorrent-nox
```

Tambahkan User yang akan digunakan login pada grup `qbittorrent-nox`, dalam hal ini nama user saya adalah `joenmarz`
```bash
sudo adduser joenmarz qbittorrent-nox
```

Enable dan Restart service dengan mengetikkan pada terminal
```bash
sudo systemctl daemon-reload
sudo systemctl enable qbittorrent-nox.service
sudo systemctl restart qbittorrent-nox.service
```

Pastikan service telah berjalan baik dengan mengetikkan
```bash
sudo systemctl status qbittorrent-nox.service
```
Jika service berjalan dengan baik akan muncul tampilan seperti ini:
```bash
● qbittorrent-nox.service - qbittorrent-nox terminal application
     Loaded: loaded (/etc/systemd/system/qbittorrent-nox.service; enabled; vendor preset: enabled)
     Active: active (running) since Sat 2022-10-29 02:01:40 PST; 2s ago
    Process: 75570 ExecStart=/usr/bin/qbittorrent-nox -d --webui-port=6969 (code=exited, status=0/SUCCESS)
   Main PID: 75571 (qbittorrent-nox)
      Tasks: 11 (limit: 7069)
     Memory: 6.6M
        CPU: 95ms
     CGroup: /system.slice/qbittorrent-nox.service
             └─75571 /usr/bin/qbittorrent-nox -d --webui-port=6969
```

qBittorrent-nox web user interface sudah bisa digunakan. Untuk menjalankan cukup mengetikkan pada web browser anda `localhost:6969` secara lokal, atau dari PC lain dengan mengetikkan ip address host anda diikuti port 6969 `192.x.x.x:6969`

Saat login pertama kali, user bawaannya adalah `admin` dan passwordnya `adminadmin`. Anda dapat mengubah user pada pengaturan web interface qBittorrent-nox setelah login.

## Referensi
- [YT SKaii Nyght tentang qBitTorrent-nox on Headless Debian - Let's Install](https://www.youtube.com/watch?v=NQ3T-2Xf9-c)
