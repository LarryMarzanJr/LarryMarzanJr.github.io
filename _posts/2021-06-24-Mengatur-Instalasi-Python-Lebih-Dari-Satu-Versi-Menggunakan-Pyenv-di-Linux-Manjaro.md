---
layout: post
title:  "Mengatur Instalasi Python Lebih Dari Satu Versi Menggunakan Pyenv di Linux Manjaro"
date:   2021-06-24 08:33:00 +0800
tags: [Python]
---

## Cara install
Instalasi pyenv di Manjaro menggunakan helper pamac:
```bash
pamac install pyenv
```

Atau instalasi pyenv di Manjaro menggunakan helper pamac:
```bash
pacman -S pyenv
```

## List versi python
Untuk melihat versi python secara keseluruhan menggunakan:
```bash
pyenv install --list
```
Tapi ini akan sangat panjang karena versi python sangat banyak.
Untuk itu coba list versi python dengan list yang lebih pendek, misalnya versi 3.6.x sampai dengan 3.9.x. Gunakan perintah berikut:
```bash
pyenv install --list | grep " 3\.[6789]"
```