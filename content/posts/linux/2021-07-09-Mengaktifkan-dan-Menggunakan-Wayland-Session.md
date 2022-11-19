---
title: "Mengaktifkan Wayland Session di Linux"
subtitle: ""
date: 2021-07-09T12:41:00+08:00
lastmod: 2021-07-09T12:41:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [linux]
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

# Mengaktifkan Wayland Session di Linux
Mengapa Menggunakan Wayland Session?

1. Jika menggunakan GPU NVIDIA maka Xorg tidak mensupport graphics tersebut
2. Jika Menggunakan Xorg pada Ubuntu & Pop OS (Debian) maka display anda akan menjadi _laggy_ seakan-akan graphic card belum terinstall, padahal karena tidak disupport Xorg.

Dengan alasan tersebut maka kita menggunakan Wayland Session. Caranya adalah dengan mengedit file pada `/etc/gdm3/custom.conf`. Pada baris bertuliskan `WaylandEnable=false`, tambahkan tanda pagar `#` sehingga Wayland Session bisa berfungsi:
```
# WaylandEnable=false
```

Setelah itu restart komputer anda. Pada saat akan login, klik pada icon _gear_ atau gerigi, biasanya pada pojok kanan bawah setelah kita mengklik user login. Ganti menjadi `Wayland Session`, kemudian login seperti biasa.

Anda akan merasakan bedanya, OS Linux anda tidak akan _laggy_ seperti sebelumya.

Sumber:

[Reddit.com - how do i start wayland session](https://www.reddit.com/r/pop_os/comments/75wn18/how_do_i_start_wayland_session/){:target="_blank"} 
