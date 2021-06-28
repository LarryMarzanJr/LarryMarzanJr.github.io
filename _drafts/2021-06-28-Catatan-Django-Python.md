---
layout: post
title:  "Cara Mudah Menggunakan Django Framework"
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

## Mengaktifkan Virtual Environment
Untuk menggunakan virtual environment, kita perlu masuk ke dalam direktori virtual environment, dalam hal ini yang kita buat adalah `django207-venv-py365`, untuk itu ketikkan
```bash
cd django207-venv-py365
```
Kemudian aktifkan virtual environment dengan mengetikkan
```bash
source bin/activate
```
Virtual Environment Django Framework siap digunakan.

## Membuat Project Django
Setelah virtual environment aktif, kita sudah bisa memulai project kita. setelah masuk ke dalam direktori environment `django207-venv-py365`, kita buatkan 1 direktori baru untuk menampung project kita. Dalam hal ini saya menamainya `src`, kemudian kita masuk ke dalam direktori tersebut:
```bash
mkdir src
cd src
```
