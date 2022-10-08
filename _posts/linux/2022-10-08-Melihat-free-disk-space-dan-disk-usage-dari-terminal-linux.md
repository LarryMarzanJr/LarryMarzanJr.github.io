---
layout: post
title:  "Melihat Free Disk Space dan Disk Usage Melalui Terminal atau CLI Menggunakan Perintah df"
date:   2022-10-08 06:13:00 +0800
category: linux
---

## Daftar Isi  
[Melihat Total, Ketersediaan dan Penggunaan Disk](#df_intro)

[Referensi](#reference)



<a name="df_intro"/>

## Melihat Total, Ketersediaan dan Penggunaan Disk

```bash
df
```

Jika ingin melihat disk usage dalam satuan megabytes, anda gunakan tag `-BM`, dalam gigabytes `-BG`. Contoh:
```bash
df -BM
```
Human readable atau dapat dibaca oleh bahasa manusia biasanya menambahkan tag `-h`
```bash
df -h
```
```bash
df -i
```
```bash
df -T
```
Mengecualikan filesystem tertentu (exclude)
```bash
df -x <filesystem>
```
Mengecualikan filesystem tertentu dan menambahkan total di paling bawah
```bash
df -x <filesystem> --total
```
Menampilkan disk dengan filesystem tertentu saja
```bash
df -t <filesystem>
```
Menampikan disk partisi tertentu
```bash
df /dev/sdX1
```



<a name="reference"/>

## Referensi
- [howtogeek.com tentang How to View Free Disk Space and Disk Usage From the Linux Terminal](https://www.howtogeek.com/409611/how-to-view-free-disk-space-and-disk-usage-from-the-linux-terminal/){:target="_blank"}
