---
title:  "Menggunakan Tmux"
subtitle: ""
date:   2022-02-26T23:51:00+08:00
lastmod:   2022-02-26T23:51:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [linux]
categories: [tmux]

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

# Menggunakan Tmux

## Apa itu Tmux?

Tmux adalah aplikasi yang memungkinkan kita membuat session tersendiri di dalam terminal shell. Session tersebut bisa kita biarkan berjalan walaupun terminal sudah diclose. Keuntungan memakai session tmux salah satunya ketika kita mengakses shell secara remote menggunakan ssh, kita bisa mengakses session tmux yang sedang aktif.

Untuk menginstall tmux pada distro linux anda, silahkan melihat referensi pada [repository resmi tmux](https://github.com/tmux/tmux/wiki/Installing)


## Membuat Session Baru
### Session Baru
Untuk membuat session baru di Tmux jalankan
```bash
> tmux
```
### Session Baru dengan label Nama
Untuk membuat session baru yg memiliki label nama di Tmux jalankan
```bash
> tmux new -s nama_session_anda
```

## Membuka Tmux Session

Untuk memperoleh daftar session yang sedang aktif dalam sebuah [shell](https://www.tutorialspoint.com/unix/unix-what-is-shell.htm), gunakan perintah `tmux ls`
```bash
> tmux ls
0: 1 windows (created Sat Feb 26 23:51:00 2022)
```
Diatas menunjukan ada satu session tmux yang sedang aktif yaitu session 0. Jika ada lebih dari satu session maka akan muncul `0: ..`, `1: ..`, `2: ..` dan seterusnya. Untuk memilih session 0 kita gunakan perintah berikut
```bash
> tmux attach-session -t 0
```
dan ini akan membuka session 0 yang sedang aktif.

## Referensi
[medium.com tentang What is tmux and why would you want it for frontend development?](https://medium.com/@tholex/what-is-tmux-and-why-would-you-want-it-for-frontend-development-e43e8f370ef2)

[poopcode.com tentang attach to tmux session](https://poopcode.com/attach-to-tmux-session/)
