---
title:  "Setup Samba Server Di Debian 11"
subtitle: ""
date:   2022-10-13T01:23:00+08:00
lastmod:   2022-10-13T01:23:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [smb]
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

## Daftar Isi  
[Proses Instalasi SMB server di Debian](#installation)

[Konfigurasi Security Policy pada Windows 10](#win10config)

[Referensi](#reference)


<a name="installation"/>

## Proses Instalasi SMB server di Debian

Install package Samba
```bash
sudo apt install samba
```

Konfigurasi sharing folder pada samba service dilakukan di `/etc/samba/smb.conf`.
```bash
sudo nano /etc/samba/smb.conf
```
Kemudian pada bagian bawah file tambahkan argumen berikut:
```
# additional share for my Hardisk
[datastore]
 path = /srv/pool/datastore
 force group = nogroup
 create mask = 0755
 directory mask = 0755
 browsable = yes
 writeable = yes
 guest ok = yes
```

Struktur folder harus kita ubah sehingga semua user termasuk guest dapat mengakses folder sharing ini:
```bash
sudo chown nobody:nogroup /srv/pool/datastore
```

<a name="win10config"/>

## Konfigurasi Security Policy pada Windows 10

```
Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters
```
Edit atau tambahkan binary DWORD `AllowInsecureGuestAuth` dan ubah value data menjadi `1`.

<a name="reference"/>

## Referensi
- [Novaspirit Tech YT tentang DIY NAS Server Setup with Debian / Plex / Raid 5 / Steam Library Caching / UrBackup / SMB Part 2](https://www.youtube.com/watch?v=cSi-NOlomLc&t=696s)
- [Tech Review Tech YT tentang Windows 10 You Can't Access This Shared Folder Because Your Organization's Security Policies Block Unauthenticated Guest Access.](https://www.youtube.com/watch?v=vyatMj1Z2NQ)
