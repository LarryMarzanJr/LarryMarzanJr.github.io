---
title:  "Menambahkan Fungsi Helpers di Laravel"
subtitle: ""
date: 2024-03-05T11:05:00+08:00
lastmod: 2024-03-05T11:05:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [php, laravel, debian]
categories: [php]

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

# Menambahkan Fungsi Helpers di Laravel

## Membuat file helpers.php

Secara default, Laravel sudah memiliki fungsi / helper yang disediakan untuk kita gunakan. Namun ada kalanya kita membutuhkan custom helper buatan sendiri untuk digunakan secara berulang.

Cara menambahkan helpers custom yaitu dengan membuat direktori dan file `Helpers/helpers.php` yang akan kita taruh pada project directory kita di `app/Http/`
```bash
mkdir app/Http/Helpers/helpers.php
```
Di dalam file helpers tersebut kita bisa menambahkan fungsi yang kita butuhkan
```php
<?php

// tambahkan fungsi anda di sini

```

## Mendaftarkan File helpers.php di composer.json
Sebelum helpers bisa kita gunakan, kita perlu mendaftarkan file helpers.php pada file `composer.json` kita perlu mendaftarkan file helpers.php agar dapat digunakan. Tambahkan pada bagian autoload:
```json
"autoload": {
        ...

        "files": [
            "app/Http/Helpers/helpers.php"
        ],
    },
```
Setelah ditambahkan, kita perlu melakukan dump autoload pada composer, baru helpers bisa berfungsi.
```bash
composer dump autoload
```

## Referensi

`...`