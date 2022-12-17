---
title: "Install Homebrew Di Debian 11"
subtitle: ""
date: 2022-12-17T15:35:11+08:00
lastmod: 2022-12-17T15:35:11+08:00
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: []
categories: []

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

## Persiapan

Update Debian 11:
```bash
sudo apt update
sudo apt upgrade
```

Setelah itu install package yang diperlukan sebelum menginstall Homebrew.
```bash
sudo apt install build-essential procps curl file git
```

## Install Homebrew
Then, we can install Homebrew by executing this command which downloads and executes the installation script recommended by the developers.
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Setelah proses download dan instalasi selesai, akan muncul pesan **Installation
successful!**.
The only caveat is that the folder where Homebrew will save the binaries is not in the path. To fix this, run each of these commands.
Path pada debian untuk instalasi Homebrew perlu diperbaiki. Jalankan perintah berikut:
```bash
test -d ~/.linuxbrew && eval "$(~/.linuxbrew/bin/brew shellenv)"
test -d /home/linuxbrew/.linuxbrew && eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
test -r ~/.bash_profile && echo "eval "$($(brew --prefix)/bin/brew shellenv)\"" >> ~/.bash_profile
echo "eval "$($(brew --prefix)/bin/brew shellenv)\" >> ~/.bash_profile
```

Untuk memastikan Homebrew telah terinstall dengan baik, jalankan instalasi pertama anda
```bash
brew install hello
```

Dan jalankan aplikasi yang baru diinstall
```bash
hello
Hello, world!
```

Homebrew sudah siap digunakan.

# Referensi
[UnixCop - How to install Homebrew on Debian 11](https://unixcop.com/install-homebrew-debian/)
