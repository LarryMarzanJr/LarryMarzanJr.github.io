---
title: "Membuka Akses Situs Reddit.com di Indonesia"
subtitle: ""
date: 2018-04-01T00:00:00+08:00
lastmod: 2018-04-01T00:00:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [hosts]
categories: [internet]

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

# Cara membuka Akses Situs Web Reddit.com
[Reddit.com](https://www.reddit.com/) tidak bisa langsung dibuka di Indonesia. Oleh karenanya ada cara mudah untuk mengakalinya, yaitu dengan mengedit file hosts.

Pada Windows lokasi file hosts terdapat di: `C:\Windows\System32\drivers\etc\hosts`.

Pada Linux dan Mac file hosts terdapat di: `/etc/hosts`.

Buka file hosts tersebut dan tambahkan host reddit dibawah:
```
## Reddit
151.101.129.140 reddit.com
151.101.129.140 ww.reddit.com
151.101.129.140 www.reddit.com
151.101.129.140 ssl.reddit.com
151.101.129.140 blog.reddit.com
151.101.129.140 forum.reddit.com
151.101.129.140 help.reddit.com
151.101.129.140 test.reddit.com
151.101.129.140 pay.reddit.com
151.101.129.140 en.reddit.com
151.101.129.140 en-us.reddit.com
151.101.129.140 4x.reddit.com
151.101.85.140 m.reddit.com
151.101.129.140 np.reddit.com
151.101.129.140 nsfw.reddit.com
151.101.129.140 oauth.reddit.com
54.174.14.76 out.reddit.com
54.172.97.229 redd.it
151.101.85.140 i.redd.it
54.173.170.4 pixel.redditmedia.com
```
Dan selesai! Situs [Reddit.com](https://www.reddit.com/) kini sudah bisa dibuka di browser anda!
