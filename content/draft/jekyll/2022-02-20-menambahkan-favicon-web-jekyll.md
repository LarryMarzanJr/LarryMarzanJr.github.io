---
categories: jekyll
date: "2022-02-20T21:38:00Z"
tags: jekyll
title: Menambahkan favicon di Web Jekyll Anda
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
