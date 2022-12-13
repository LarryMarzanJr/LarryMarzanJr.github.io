# Menambahkan Keyserver di Arch Linux AUR


## Menambahkan keyserver di Archlinux

Terkadang saat kita menginsall package di Archlinux menggunakan helper AUR, kita diminta harus menambahkan keyserver sendiri. Kebanyakan proses dilkukan secara otomatis. Namun ketika anda diminta untuk memasukkan keyserver secara manual, maka perintahnya sebagai berikut

gpg --keyserver pool.sks-keyservers.net --recv-keys <key_server>

Contoh, ketika harusa memasukkan keyserver Spotify secara manual maka:

```
gpg --keyserver pool.sks-keyservers.net --recv-keys 931FF8E79F0876134EDDBDCCA87FF9DF48BF1C90
```

dimana `931FF8E79F0876134EDDBDCCA87FF9DF48BF1C90` adalah keyserver dari package Spotify.

Setiap package mempunyai keyserver yang berbeda, anda harus meng-copy keyserver dari masing-masing package ketika diminta. Biasanya keyserver muncul pada saat kita melakukan proses instalasi melalui shell (terminal).


