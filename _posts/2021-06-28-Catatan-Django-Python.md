---
layout: post
title:  "Step By Step Menggunakan Django Framework"
date:   2021-06-28 16:38:00 +0800
tags: [Django Framework]
---

## Persiapan awal
Tutorial ini cocok diikuti menggunakan `Python 3.6.5` dan `django 2.0.7`.

Sebaiknya menginstall multi-versi dari python menggunakan pyenv agar versi python yang terinstall di system tidak akan terganggu. Lihat artikel Mengatur Instalasi Python Lebih Dari Satu Versi Menggunakan Pyenv di Linux untuk informasi lebih lanjut.

## Buat Virtual environment
Buat virtual environment khusus untuk project django 
dengan `python 3.6.5` dan `django 2.0.7`.

Untuk membuat virtual environment ketikkan:
```bash
python -m venv <nama_virtual_environment>
```
Misalnya nama virtual environmentnya saya namakan `django207-venv-py365`, maka perintah untuk membuat virutal environment menjadi:
```bash
python -m venv django207-venv-py365
```
Nama virtual environment bisa apa saja. Tapi untuk referensi saya, nama environment saya gunakan `django207-venv-py365` agar mudah diketahui bahwa virtual environment yang saya buat menggunakan versi `django 2.0.7` dan `python 3.6.5`.

Untuk menggunakan virtual environment, kita perlu masuk ke dalam direktori virtual environment, dalam hal ini yang kita buat adalah `django207-venv-py365`, untuk itu ketikkan
```bash
cd django207-venv-py365
```
Kemudian aktifkan virtual environment dengan mengetikkan
```bash
source bin/activate
```