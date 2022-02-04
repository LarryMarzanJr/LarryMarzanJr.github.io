---
layout: post
categories: games
date: 2021-08-11 10:08:00 +0800
#excerpt: ''
#image: 'BASEURL/assets/blog/img/.png'
#description:
#permalink:
title: 'Steam Cache untuk menyimpan Game hasil Download'
---

# Latar Belakang
Mengapa Menggunakan Steam Cache?

1. Jika kita mendownload game steam yang sangat besar, kemudian reinstall kembali di kemudian hari maka membutuhkan waktu serta quota internet yang lumayan besar
2. Dengan adanya steam cache server, kita bisa mengemat waktu karena ketika download kembali game tersebut kita sudah memiliki backup tanpa harus download ulang lewat internet, melainkan secara lokal dari server kita

Dengan alasan tersebut maka kita menggunakan Steam Cache. 

# Instalasi

## Install Docker

## Install lancache
Install lancache:
```
not yet...
```
Run lancache:
```bash
sudo docker run --restart unless-stopped --name lancache --detach -v /srv/pool/cache:/data/cache -v /srv/pool/cache/logs:/data/logs -p 80:80 lancachenet/monolithic:latest
```

## Install lancache-dns
Install lancache-dns:
```
not yet...
```

Run lancache-dns:
```bash
sudo docker run --restart unless-stopped --name lancache-dns --detach -p 53:53/udp -e USE_GENERIC_CACHE=true -e LANCACHE_IP=192.168.2.2 lancachenet/lancache-dns:latest
```

IP `192.168.2.2` adalah server kita dimana steam cache terinstall.

## Lancache log
Untuk melihat log file lancache, jalankan perintah
```bash
sudo docker exec -it lancache tail -f /data/logs/access.log
```

Sumber:

[Youtube.com - Steam Library Caching](https://www.youtube.com/watch?v=cSi-NOlomLc&t=1229s){:target="_blank"} 