---
title: "Cara Install Nodejs NPM di Linux Debian"
categories: package-manager
tags: npm
date: 2022-02-12T06:35:00+08:00
---

# Cara Install Nodejs NPM di Linux Debian
Pada terminal, ketikkan:
```
sudo apt install nodejs npm
```

Setelah itu tambahkan tulisan ini pada file `.bashrc` anda:
```
npm set prefix ~/.npm
PATH="$HOME/.npm/bin:$PATH"
PATH="./node_modules/.bin:$PATH"
```
