---
layout: post
tags: [Git]
categories: [Package Manager]
date: 2020-09-23 18:56:00 +0800
#excerpt: ''
#image: 'BASEURL/assets/blog/img/.png'
#description:
#permalink:
title: 'Reset Repositori Git Lokal Mengikuti Repositori Remote'
---

<!-- Sumber: -->
<!-- https://stackoverflow.com/questions/1628088/reset-local-repository-branch-to-be-just-like-remote-repository-head -->

Katakanlah anda "blunder" pada mengedit repositori lokal dan ingin meresetnya sesuai Repositori yang tersimpan terakhir di Web anda. Lakukan perintah ini:
```bash
git fetch origin
git reset --hard origin/main
```

Sebaliknya, katakanlah repositori lokal saat ini ingin anda simpan sementara, atau belum live, maka simpanlah di branch tersendiri sebagai backup. Lakukan perintah ini:
```
git commit -a -m "Simpan Pekerjaan saya, untuk jaga-jaga"
git branch simpan-kerjaan
```