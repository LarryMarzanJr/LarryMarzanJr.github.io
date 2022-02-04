---
layout: post
title:  "Persiapan Membangun Gitlab Pages Menggunakan Jekyll di ArchLinux"
date:   2020-09-17 04:40:00 +0800
categories: gitlab
---


## Pengaturan Local Environment Untuk Membangun GitLab Pages

Untuk membangun GitLab Pages secara offline atau remote kita perlu mengatur *Environment* Lokal di komputer kita. Beberapa aplikasi yang perlu diinstall yaitu:

- Git Client
- AUR
- Jekyll
- Text Editor

Untuk menginstall di Arch Linux, petunjuk dan kegunaan masing-masing aplikasi dijelaskan sebagai berikut:

# Git Client
Git Client merupakan aplikasi utama yang digunakan ketika kita akan melakukan *clone* atau unduh repositori yang kita buat, kemudian mengeditnya secara lokal atau *offline*.
Cara menginstallnya sebagai berikut:
```
sudo pacman -S git
```
# AUR
AUR atau *Arch User Repository* adalah *Package Manager* yang dibutuhkan agar *Jekyll* bisa diinstall. Ada beberapa alternatif AUR package manager. Saya lebih merekomendasi `yay` package manager.
Cara menginstallnya sebagai berikut:
```
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```
Setelah AUR terinstall kita bisa menginstall Package dengan perintah `yay -S nama_package`

# Jekyll
Jekyll bisa dibilang sebuah *framework* atau kerangka dasar dalam membangun Website berbasis Bahasa Pemrograman [Markdown](https://en.wikipedia.org/wiki/Markdown "Markdown Wiki").
Cara menginstallnya sebagai berikut:
```
yay -S jekyll
```
# Text Editor
Text Editor merupakan tempat dimana anda akan menulis artikel atau content anda menggunakan Bahasa Pemrograman [Markdown](https://en.wikipedia.org/wiki/Markdown "Markdown Wiki"){:target="_blank"}. Penggunaan Markdown sangat mudah, berikut ini adalah [referensi Markdown](# "Markdown Cheatsheet")

Text editor tidak harus sama. Rekomendasi saat ini, text editor GUI based yang paling populer adalah [Code](https://code.visualstudio.com){:target="_blank"}. Dan untuk pengguna tingkat lanjut biasanya lebih suka menggunakan [Vim](https://www.vim.org){:target="_blank"} sebagai text editor.

<!-- Untuk menginstal Code -->

<!-- Mac OS
# Install GitLab Client
GitLab Client merupakan aplikasi utama yang digunakan ketika kita akan melakukan *clone* atau unduh repositori yang kita buat, kemudian mengeditnya secara lokal atau *offline*.

Mac OS:
Dengan menggunakan [homebrew](https://brew.sh){:target="_blank"} anda dapat menginstall GitLab Client. Jika homebrew belum terinstall, maka jalankan perintah:
```
/bin/bash -c "$(curl -fsSL https://raw.GitLabusercontent.com/Homebrew/install/master/install.sh)"
```
Kemudian lanjutkan dengan menginstall GitLab Client
```
brew install git
```
# Install Ruby

sudo pacman -S ruby
# Install Jekyll
# Install Text Editor -->