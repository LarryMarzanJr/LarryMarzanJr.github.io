---
categories: python
date: "2021-06-24T08:33:00Z"
title: Mengatur Instalasi Python Lebih Dari Satu Versi Menggunakan Pyenv di Linux
---

## Pre-Requisites
Agar pyenv berjalan dengan baik di Linux, kita perlu menginstall beberapa package library. Masing-masing turunan distro diinstal dengan cara berbeda.

Turunan Ubuntu/Debian:
```bash
sudo apt install -y libedit-dev libncurses5-dev \
install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python3-openssl
```
Fedora/CentOS/RHEL(aws ec2):
```
sudo yum install compat-openssl10-devel --allowerasing
```
Turunan Archlinux, Manjaro dsb.:
menggunakan AUR helper, dalam hal ini jika menggunakan YAY:
```bash
yay -S ncurses5-compat-libs 
```

## Cara install
Instalasi lebih dianjurkan menggunakan git:
```bash
 git clone https://github.com/pyenv/pyenv.git ~/.pyenv
```
(sumber: https://github.com/pyenv/pyenv#installation)

Kemudian tambahkan PATH pada environment shell anda. Tergantung jika anda menggunakan Bash atau Zsh atau fish shell.
Jika anda menggunakan Bash:
```bash
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init --path)"' >> ~/.bashrc
```
Jika anda menggunakan Zsh:
```bash
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zprofile
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zprofile
echo 'eval "$(pyenv init --path)"' >> ~/.zprofile
```
Jika and menggunakan Fish Shell:
Jalankan dahulu kedua perintah ini satu per satu
```bash
set -Ux PYENV_ROOT $HOME/.pyenv
set -U fish_user_paths $PYENV_ROOT/bin $fish_user_paths
```
Kemudian tambahkan pada file konfigurasi yang terletak di ~/.config/fish/config.fish:
```bash
status is-login; and pyenv init --path | source
```
Setelah itu restart shell anda. instalasi selesai.

## Instalasi Pyenv
Untuk mulai menginstall python sesuai versi yang anda inginkan:
```bash
pyenv install -v x.x.x
```
dimana `x.x.x` diganti dengan versi python yang akan diinstall

Untuk melihat versi python mana saja yang sudah anda install:
```bash
pyenv versions
```
## List versi python di pyenv
Untuk melihat versi python secara keseluruhan menggunakan:
```bash
pyenv install --list
```
Tapi ini akan sangat panjang karena versi python sangat banyak.
Untuk itu coba list versi python dengan list yang lebih pendek, misalnya versi 3.6.x sampai dengan 3.9.x. Gunakan perintah berikut:
```bash
pyenv install --list | grep " 3\.[6789]"
```
## Cara Menggunakan Pyenv, mengganti ke versi python tertentu
Untuk menggunakan versi python yang anda inginkan, anda haru install versi python tersebut menggunakan `pyenv install x.x.x`. Seandainya anda ingin menggunakan python versi 3.8.10 maka install dengan perintah `pyenv install 3.8.10`.

Setelah itu untuk mengganti python ke versi yang inginkan, dalam hal ini `3.8.10` maka gunakan perintah
```bash
pyenv global 3.8.10
```