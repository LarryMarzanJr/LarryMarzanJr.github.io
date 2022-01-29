---
layout: post
categories: [post, internet]
date: 2018-04-01 00:00:00 +0800
#excerpt: ''
#image: 'BASEURL/assets/blog/img/.png'
#description:
#permalink:
title: 'Membuka Akses Situs Reddit.com di Indonesia'
---

# Cara membuka Akses Situs Web Reddit.com
[Reddit.com](https://www.reddit.com/){:target="_blank"} tidak bisa langsung dibuka di Indonesia. Oleh karenanya ada cara mudah untuk mengakalinya, yaitu dengan mengedit file hosts.

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
Dan selesai! Situs [Reddit.com](https://www.reddit.com/){:target="_blank"} kini sudah bisa dibuka di browser anda!