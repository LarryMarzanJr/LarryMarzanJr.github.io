---
title: "Menambahkan favicon di Web Jekyll Anda"
subtitle: ""
date: 2022-02-20T21:38:00+08:00
lastmod: 2022-02-20T21:38:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [jekyll]
categories: [static-site-generator]

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

### File favicon.png
Tambahkan file favicon pada root directory website jekyll anda.

### Tambahkan link favicon
Tambahkan link favicon pada `head.html` biasanya terletak di `_includes/head.html` script berikut:
```html
	<link rel="shortcut icon" type="image/png" href="favicon.png">
```
Sehingga file `head.html` menjadi:
```html
<head>
	<meta charset="utf-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<!-- Tambahkan favicon pada 1 baris dibawah ini -->
	<link rel="shortcut icon" type="image/png" href="favicon.png">
    
	...
</head>
```

Selamat mencoba.


## Referensi
- [Youtube - Github Pages Add a Favicon](https://www.youtube.com/watch?v=4v-8_JSydgk){:target="_blank"}
