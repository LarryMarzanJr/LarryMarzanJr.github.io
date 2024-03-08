---
title:  "Menyimpan Session Tmux"
subtitle: ""
date: 2024-03-07T13:02:00+08:00
lastmod: 2024-03-07T13:02:00+08:00
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

# Menyimpan Session Tmux

## Membuat Session Tmux Menggunakan Nama

Kita perlu menamakan session agar memudahkan ketika session tersebut akan dipanggil kembali.
Gunakan perintah berikut:
```bash
tmux new -s 'my session'
```
Setelah itu kita akan session tersebut akan otomatis terbuka. Perlu diketahui bahwa session
ini masih bersifat sementara, artinya ketika kita exit dari terminal maka session ini akan
hilang. Untuk itu kita perlu menginstall plugin tmux yang dapat menyimpan session
`my session` tersebut. Lakukan dettach session dengan menekan `Ctrl + b` kemudian `d`.
Setelah itu lanjut dengan instalasi plugin.

## Plugin Manager

Untuk menyimpan session kita perlu menambahkan plugin di Tmux. Namun untuk menambahkan
plugin, kita perlu menginstall plugin manager. Download plugin dengan mengetikkan:
```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

Kemudian buat file konfigurasi `.tmux.conf` pada home folder
```bash
nvim ~/.tmux.conf
```
dan tambahkan konfigurasi di dalamnya:
```
# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
 
# Other examples:
# set -g @plugin 'github_username/plugin_name'
# set -g @plugin 'git@github.com/user/plugin'
# set -g @plugin 'git@bitbucket.com/user/plugin'
 
# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run -b '~/.tmux/plugins/tpm/tpm'
```

## Plugin Untuk Menyimpan Session
Setelah plugin manager diinstall, tambahkan plugin
[Tmux-Resurrect](https://github.com/tmux-plugins/tmux-resurrect) pada file `.tmux.conf`
```
set -g @plugin 'tmux-plugins/tmux-resurrect'
```
Setelah itu kita perlu menginstall plugin yang sudah ditambahkan tadi. Masuk ke session
tmux `my session` yang telah kita bentuk dari awal
```bash
tmux attach-session -t 'my session'
```
Setelah masuk di session tersebut tekan `Ctrl + b` kemudian `Ctrl + I` (huruf "i" kapital) agar
plugin akan diinstal. Dan jika sudah berhasil install maka akan muncul pesan
```bash
TMUX environment reloaded.
Done, press ESCAPE to continue.
```

## Menyimpan dan Memanggil Session

### Simpan Session
Untuk menyimpan session kita hanya perlu menekan `Ctrl + b` kemudian `Ctrl + s`

### Pilih Session
Kita bisa membuat sebanyak mungkin session dan menyimpannya. Untuk memanggil session yang
kita inginkan tekan `Ctrl + b` kemudian `s`, maka list session yang sudah disimpan akan
muncul dan dapat dibuka kembali.

### Restore Session
Session yang telah kita simpan terdapat di `~/.tmux/ressurect`. Apabila dalam kondisi
komputer kita telah direstart, saat kita mencari session yang disimpan dengan `tmux ls`,
maka kita tidak bisa langsung menemukannya. Sehingga kita perlu me-restore sessions
tersebut. Caranya dengan membuka tmux seperti biasa.
```bash
tmux
```
Dari dalam session tersebut lakukan restore session dengan menekan `Ctrl + b`
kemudian `Ctrl + R`. Jika berhasil restore maka akan muncul pesan:
```
Tmux restore complete!
```
## Referensi

[MakeTechEasier tentang How to Manage and Restore Tmux Sessions in Linux](https://www.maketecheasier.com/manage-restore-tmux-sessions-linux/)

[StackExchange tentang How to save multiple sessions in tmux](https://superuser.com/questions/1010075/how-to-save-multiple-sessions-in-tmux/1287933#1287933)
