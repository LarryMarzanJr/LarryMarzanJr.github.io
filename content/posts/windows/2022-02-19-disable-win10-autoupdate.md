---
title: "Cara disable auto update pada Windows 10"
subtitle: ""
date: 2022-02-19T15:33:00+08:00
lastmod: 2022-02-19T15:33:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [windows]
categories: [windows]

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

<
### Disable Windows Update pada menu Services
Klik `Start` kemudian ketikkan `services`. Double klik pada `Windows Update` kemudian ubah startup type menjadi `disabled` dan apply settingan anda.

### Disable Windows Update pada menu Registry
Tekan tombol `Win + R`, ketikkan `regedit` dan tekan `Enter`. Dari menu Regedit kita buka menu tree berikut:
```
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\wuauserv
```
##### ImagePath
Double klik pada `ImagePath` kemudian pada value data
```
%systemroot%\system32\svchost.exe -k netsvcs -p
```
ubah `svchost.exe` menjadi `svchost0.exe` sehingga value data menjadi:
```
%systemroot%\system32\svchost0.exe -k netsvcs -p
```
##### DependOnService
Double klik pada `DependOnService` kemudian pada value data `rpcss` diganti menjadi `rpcss0`.

Sampai disini auto update Windows 10 telah berhasil dinonaktifkan.

## Referensi
- [Youtube - How to Disable the Latest Windows 10 Update 2020](https://www.youtube.com/watch?v=0qQMpsfj2hw&t=284s)
