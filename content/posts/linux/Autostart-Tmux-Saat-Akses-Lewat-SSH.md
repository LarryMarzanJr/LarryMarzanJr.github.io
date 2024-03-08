---
title: "Autostart Tmux Saat Akses Lewat SSH"
subtitle: ""
date: 2022-11-19T12:23:26+08:00
lastmod: 2022-11-19T12:23:26+08:00
author: ""
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

## Kegunaan
Ketika kita menjalankan login lewat `SSH`, kita bisa menggunakan session manager dengan
membuka aplikasi `Tmux`. Namun jika Tmux sering anda gunakan maka anda dapat menjalankannya
secara otomatis saat login SSH.

## Edit Konfigurasi Shell
Untuk menjalankan Tmux secara otomatis saat login SSH, maka tambahkan perintah pada shell
profile anda. Jika menggunakan `bash` maka dapat diedit dari file `.bashrc`. Jika
menggunakan `zsh` maka dapat diedit dari file `.zshrc`. Tambahkan perintah berikut:
```bash
if [ -z "$TMUX" ]; then
    tmux attach -t default || tmux new -s default
fi
```

## Referensi
[Ostechnix - Autostart Tmux Session On Remote System When Logging In Via SSH](https://ostechnix.com/autostart-tmux-session-on-remote-system-when-logging-in-via-ssh/)
