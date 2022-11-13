---
title: "Cara Install Docker Container di Linux Ubuntu"
subtitle: ""
date: 2022-02-12T18:06:00+08:00
lastmod: 2022-02-12T18:06:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [docker]
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

### Apa itu docker?
Docker adalah container environment virtual yang digunakan sebagai versioning terhadap aplikasi yang sedang anda kembangkan. Ada banyak aplikasi container yang tersedia, namun saat ini kita akan bahas khusus Docker saja dulu.

### Mengapa versioning?
Karena kita tahu bahwa setiap aplikasi selalu memiliki update, dan aplikasi yang kita sedang kembangkan sangat bergantung pada versi aplikasi pengembang yang saat itu kita gunakan.
Seiring waktu saat sistem operasi kita diupdate secara global, versi aplikasi pengembang pun ikut terupdate, mengakibatkan aplikasi yang sedang kita buat bisa rusak karena tidak lagi kompatibel dengan versi terupdate. Disinilah container, dalam hal ini Docker, membantu membuat kita sebuah environment virtual khusus yang dapat memenuhi kebutuhan versi aplikasi pengembang sesuai dengan versi aplikasi yang kita kembangkan.

### Instalasi Docker di Linux Ubuntu menggunakan Repository
##### Prasyarat
Untuk menginstall docker di Linux [Ubuntu](https://ubuntu.com/download/desktop){:target="_blank"} anda perlu menginstal setidaknya versi Ubuntu 64-bit berikut ini:
* Ubuntu Impish 21.10
* Ubuntu Hirsute 21.04
* Ubuntu Focal 20.04 (LTS)
* Ubuntu Bionic 18.04 (LTS)

##### Uninstall Docker Versi Lama
Docker versi lama yang terinstal di system anda perlu di-uninstall terlebih dahulu. Atau setidaknya untuk memastikan tidak ada docker versi lama di system anda maka perintah untuk uninstall adalah:
```bash
sudo apt remove docker docker-engine docker.io containerd runc
```
##### Setting Repositori Linux Ubuntu
Sebelum menginstall, docker memerlukan beberapa prasyarat aplikasi di Linux berupa . Update Linux anda:
```bash
sudo apt update
```
Install prasyarat Aplikasi:
```bash
sudo apt install ca-certificates curl gnupg lsb-release
```
Tambahkan GPG Key resmi dari Docker:
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
Untuk memperoleh repositori yang stabil dari Docker, jalankan perintah berikut:
```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

##### Install Docker
Setelah beberapa proses diatas, lanjutkan dengan update repository Linux,
```bash
sudo apt update
```
diikuti instalasi docker:
```bash
sudo apt install docker-ce docker-ce-cli containerd.io
```

## Referensi
[docker.com tentang Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/){:target="_blank"}
