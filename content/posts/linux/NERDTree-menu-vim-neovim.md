---
title:  "Cara Menggunakan NERDTree di Vim/Neovim"
subtitle: ""
date: 2024-03-10T08:11:00+08:00
lastmod: 2024-03-10T08:11:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [linux]
categories: [text-editor]

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
  disqus:
    enable: true
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

# Menyimpan Session Tmux

## Apa itu NERDTree?

NERDTree adalah sebuah plugin powerfull yang digunakan di Vim maupun Neovim text editor,
yang berfungsi untuk menambahkan fitur file tree atau file manager tanpa harus keluar dari
aplikasi Vim.

## Cara Menginstall Plugin NERDTree di Vim
Untuk menginstall ... `coming soon`

## Membuka NERDTree di Vim
Untuk Memanggil atau membuka NERDTree di Vim kita hanya perlu mengetikkan `:NERDTree`.

## Mengelola File di NERDTree
Untuk mengelola file, setelah NERDTree dibuka, kita tinggal menekan `m` artinya kita akan
membuka menu NERDTree, setelah itu akan muncul menu seperti dibawah:
```
NERDTree Menu. Use j/k/enter, or the shortcuts indicated                                                                                              
=========================================================                                                                                             
> (!)Execute file                                                                                                                                     
  (a)dd a childnode                                                                                                                                   
  (m)ove the current node                                                                                                                             
  (d)elete the current node                                                                                                                           
  (r)eveal the current node in file manager                                                                                                           
  (o)pen the current node with system editor                                                                                                          
  (c)opy the current node                                                                                                                             
  copy (p)ath to clipboard                                                                                                                            
  (l)ist the current node                                                                                                                             
  Run (s)ystem command in this directory  
```
Setelah menu terbuka, kita bisa melakukan perintah dasar dalam mengelola file seperti copy,
paste, move(cut). Lakukan dengan memilih menu. Kita bisa menjalankan kursor dengan menekan
`j` untuk kebawah, kemudian `k` untuk keatas lalu tekan `Enter`. Atau bisa juga menekan
huruf di dalam kurung sebagai shortcut key menu.

## Referensi
[Stackoverflow tentang Renaming or copying files and folder using NERDTree on Vim. Is it possible?](https://stackoverflow.com/questions/2295809/renaming-or-copying-files-and-folder-using-nerdtree-on-vim-is-it-possible)
