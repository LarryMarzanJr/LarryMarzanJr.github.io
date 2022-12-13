---
title: "Cara Install Nodejs NPM di Linux Debian"
subtitle: ""
date: 2022-02-12T06:35:00+08:00
lastmod: 2022-02-12T06:35:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [npm]
categories: [package-manager]

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
