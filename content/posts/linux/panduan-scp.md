---
title: "Panduan Lengkap Menggunakan SCP (Secure Copy Protocol)"
subtitle: ""
date: 2025-08-28T15:07:00+08:00
lastmod: 2025-08-28T15:07:00+08:00
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
  enable: true
  disqus:
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

# Panduan Lengkap Menggunakan SCP (Secure Copy Protocol)

## Apa itu SCP?
**SCP (Secure Copy Protocol)** adalah perintah di sistem operasi berbasis Unix/Linux yang digunakan untuk **menyalin file atau direktori antar komputer melalui jaringan** dengan aman. SCP memanfaatkan protokol **SSH (Secure Shell)** untuk melakukan otentikasi dan enkripsi data, sehingga lebih aman dibandingkan protokol lama seperti `ftp` atau `rcp`.

Dengan SCP, kita bisa:
- Menyalin file dari komputer lokal ke server remote.
- Mengambil file dari server remote ke komputer lokal.
- Menyalin file dari satu server remote ke server remote lainnya.

---

## Sintaks Dasar SCP
```bash
scp [opsi] sumber tujuan
```

- **sumber**: Lokasi file/direktori yang ingin dikopi (bisa lokal atau remote).
- **tujuan**: Lokasi tujuan penyalinan (bisa lokal atau remote).
- **opsi**: Tambahan parameter, misalnya `-r` untuk direktori, `-P` untuk port SSH custom, dll.

Format umum untuk alamat remote:
```
username@host:/path/tujuan/
```

---

## Contoh Penggunaan SCP

### 1. Menyalin file dari lokal ke server remote
```bash
scp ./alpine_int.tar joenmarz@192.168.1.88:container-alpine/
```

### 2. Menyalin file dari server remote ke lokal
```bash
scp joenmarz@192.168.1.88:container-alpine/alpine_int.tar ./
```

### 3. Menyalin direktori secara rekursif
```bash
scp -r ./backup joenmarz@192.168.1.88:/home/joenmarz/
```

### 4. Menentukan port SSH
```bash
scp -P 2222 ./alpine_int.tar joenmarz@192.168.1.88:container-alpine/
```

### 5. Menyalin antar dua server remote
```bash
scp user1@server1:/data/file.tar user2@server2:/backup/
```

---

## Opsi Penting SCP
- `-r` Menentukan port SSH custom.
- `-C` Mode verbose, menampilkan detail proses transfer.
- `-l limit` Kelebihan
- Aman karena menggunakan SSH.
- Mudah digunakan, cukup satu baris perintah.
- Mendukung copy antar remote server.

### Lebih efisien untuk sinkronisasi file.
- **sftp** Untuk sinkronisasi ke cloud storage.

---

## Kesimpulan
SCP adalah alat yang sederhana dan aman untuk menyalin file antara komputer lokal dan server remote menggunakan SSH. Dengan sintaks yang mudah, SCP cocok digunakan untuk transfer file cepat, misalnya:

```bash
scp ./alpine_int.tar joenmarz@192.168.1.88:container-alpine/
```

Namun, untuk kebutuhan transfer yang sering atau dalam jumlah besar, disarankan menggunakan `rsync` atau `sftp` agar lebih fleksibel.