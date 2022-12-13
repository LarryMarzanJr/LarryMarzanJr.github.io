---
title: "Git Branch"
subtitle: ""
date: 2022-02-07T07:50:00+08:00
lastmod: 2022-02-07T07:50:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [git]
categories: [git]

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

Biasanya dalam sebuah git repository sudah tersedia 1 branch secara default yaitu _master_ atau _main_. Namun terkadang kita perlu membuat branch baru untuk beberapa kebutuhan seperti backup project, membuat draft sub-project yang nantinya akan kita gabung (merge) ke branch utama (main), atau mungkin kita sedang membuat project dengan tim kemudian membagi tugas untuk ke masing-masing tim.

### Branch Baru (New)
Untuk membuat branch gunakan perintah:
```bash
git branch <nama-branch-baru>
```
### Pindah Branch (Checkout)
Untuk berpindah branch gunakan perintah:
```bash
git checkout <nama_branch>
```
### Gabung Branch (Merge)
Katakanlah kita memiliki sub-branch benama `branch-tambahan`.
Untuk menggabung (merge) branch `branch-tambahan`, kita perlu berpindah ke `main` branch terlebih dahulu:
```bash
git checkout main
```
Kemudian lakukan merge dengan perintah:
```bash
git merge branch-tambahan
```
### Hapus Branch (Delete)
##### Cara Menghapus Branch Lokal
Untuk menghapus branch lokal atau yang ada di PC anda, gunakan perintah:
```bash
git branch -d <nama-branch-lokal>
```
##### Cara Menghapus Branch Remote (Repositori Github)
Untuk menghapus branch yang ada di repository github anda, gunakan perintah:
```
git push origin --delete <nama-branch-remote>
```

### Copy Branch 
Untuk melakukan copy branch tertentu ke branch baru, misalnya `branch-tertentu` akan dicopy ke branch baru dengan nama misalnya `branch-baru` maka lakukan perintah
```bash
git checkout -b branch-baru branch-tertentu
```

## Referensi
[W3schools tentang git branch merge](https://www.w3schools.com/git/git_branch_merge.asp?remote=github){:target="_blank"}
[Git Tower tentang delete local branch](https://www.git-tower.com/learn/git/faq/delete-local-branch/){:target="_blank"}
[Stackoverflow tentang How can I copy the content of a branch to a new local branch?](https://stackoverflow.com/questions/14998923/how-can-i-copy-the-content-of-a-branch-to-a-new-local-branch){:target="_blank"}
