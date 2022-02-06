---
title: 'Git-Branch'
layout: post
categories: git
tags: git
date: 2022-02-06 07:50:00 +0800
---

Biasanya dalam sebuah git repository sudah tersedia 1 branch secara default yaitu _master_ atau _main_. Namun terkadang kita perlu membuat branch baru untuk beberapa kebutuhan seperti backup project, membuat draft sub-project yang nantinya akan kita gabung (merge) ke branch utama (main), atau mungkin kita sedang membuat project dengan tim kemudian membagi tugas untuk ke masing-masing tim.

### Branch Baru (New)
Untuk membuat branch gunakan perintah:
```
git branch nama-branch-baru
```
### Pindah Branch (Checkout)
Untuk berpindah branch gunakan perintah:
```
git checkout <nama_branch>
```
### Gabung Branch (Merge)
Katakanlah kita memiliki sub-branch benama `branch-tambahan`.
Untuk menggabung (merge) branch `branch-tambahan`, kita perlu berpindah ke `main` branch terlebih dahulu:
```
git checkout main
```
Kemudian lakukan merge dengan perintah:
```
git merge branch-tambahan
```

## Referensi
[W3schools tentang git branch merge](https://www.w3schools.com/git/git_branch_merge.asp?remote=github){:target="_blank"}