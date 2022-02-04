---
layout: post
categories: linux
date: 2021-07-09 12:41:00 +0800
#excerpt: ''
#image: 'BASEURL/assets/blog/img/.png'
#description:
#permalink:
title: 'Mengaktifkan Wayland Session di Linux'
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