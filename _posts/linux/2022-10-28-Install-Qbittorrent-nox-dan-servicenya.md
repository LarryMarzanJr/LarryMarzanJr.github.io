---
layout: post
title:  "Install Qbittorrent-Nox dan Servicenya"
date:   2022-10-28 19:20:00 +0800
category: linux
---

## Daftar Isi  

[Proses Instalasi](#installation)

[Menambahkan Service qBittorrent-nox](#adding-service)

[Referensi](#reference)



<a name="installation"/>

## Proses Instalasi

Proses instalasi pada debian based cukup mudah:
```bash
sudo apt update
sudo apt install qbittorrent-nox
```

<a name="adding-service"/>

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

qBittorrent-nox web user interface sudah bisa digunakan. Untuk menjalankan cukup mengetikkan pada web browser anda `localhost:6969` secara lokal, atau dari PC lain dengan mengetikkan ip address host anda diikuti port 6969 `192.x.x.x:6969`

<a name="reference"/>

## Referensi
- [YT SKaii Nyght tentang qBitTorrent-nox on Headless Debian - Let's Install](https://www.youtube.com/watch?v=NQ3T-2Xf9-c){:target="_blank"}
