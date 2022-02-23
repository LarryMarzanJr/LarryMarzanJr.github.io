---
title: 'Menggunakan Themes Jekyll Dengan Mudah'
layout: post
categories: jekyll
tags: jekyll
date: 2022-02-23 21:51:00 +0800
---

### Pilih Tema
Banyak pilihan tema yang tersedia dan di [Jekyllthemes.org](http://jekyllthemes.org/){:target="_blank"}. Jika sudah menentukan pilihan, download tema tersebut dan extract ke dalam folder project website jekyll anda. Perlu diingat kita akan membuat tema web Jekyll dari awal, jadi untuk folder project diusahakan kosong dulu lalu sebelum mengisi tema yang telah anda pilih.

### Tambahkan Environment Jekyll Pada Docker
Jika belum familiar dengan docker, maka anda wajib membaca artikel tentang [Docker disini](https://larrymarzanjr.github.io/docker/2022/02/18/install-docker-desktop-win10-integrasi-WSL-Ubuntu.html){:target="_blank"}.

Setelah itu download environment Jekyll pada [Docker Hub](https://hub.docker.com/r/jekyll/jekyll/tags){:target="_blank"}. Pada kolom Tag, pilih jekyll versi `4.0`.

Kemudian jalankan docker untuk mendownload environment jekyll 4.0 dengan perintah:
```bash
docker run --rm --volume="$PWD:/srv/jekyll" -p 4000:4000 jekyll/jekyll:4.0 jekyll serve
```

Setelah docker mendownload image Jekyll 4.0 dan menjalankannya menggunakan jekyll serve seperti perintah diatas, maka web jekyll anda telah berhasil dibuat sesuai dengan tema yang anda pilih. Anda dapat mencoba mengaksesnya secara lokal sebelum di `commit` dan `push` ke github pages.

### Docker Compose File

Perintah diatas sepertinya terlalu panjang dan jika kita mengetikkannya setiap kali menjalankan web secara lokal, sehingga kita perlu membuat `docker compose file` yang menyimpan perintah tersebut, sehingga kita hanya perlu memanggil file docker compose untuk menjalankan environment docker. Caranya adalah dengan membuat sebuah file yang kita akan namakan `docker-compose.yml` dan didalam file tersebut kita masukkan perintah sebagai berikut:
```yaml
# Script yaml di bawah fungsinya sama dengan perintah ini:
# docker run --rm --volume="$PWD:/srv/jekyll" -p 4000:4000 jekyll/jekyll:4.0 jekyll serve

version: '3'
services:
  jekyll-serve:
    image: jekyll/jekyll:4.0
    volumes:
      - '.:/srv/jekyll'
    ports:
      - 4000:4000
    command: 'jekyll serve'
```
Untuk menjalankan docker compose file kita hanya perlu mengetikkan:
```bash
docker-compose up
```
Dan untuk menghentikannya cukup menekan `control+C`.

Selamat mencoba.

## Referensi
- [Youtube - Host Your Own Blog with Jekyll, Docker, and GitHub Pages](https://www.youtube.com/watch?v=ZHQ3IwIL590&t=229s){:target="_blank"}
