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
Kemudian buat project baru dengan mengetikkan perintah
```bash
django-admin startproject <nama_project>
```
Misalnya nama project kita namakan `belajardjango` maka perintahnya adalah
```bash
django-admin startproject belajardjango
```
Projek inisial Django sudah siap digunakan. Untuk mencoba menjalankan project anda, masuk ke dalan direktori project, kemudian jalankan dengan perintah
```bash
python manage.py runserver
```
Anda akan melihat tampilan kurang lebih seperti ini:
```bash
Performing system checks...

System check identified no issues (0 silenced).

You have 14 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.

June 28, 2021 - 09:18:33
Django version 2.0.7, using settings 'trydjango.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
[28/Jun/2021 09:18:43] "GET / HTTP/1.1" 200 16348
[28/Jun/2021 09:18:43] "GET /static/admin/css/fonts.css HTTP/1.1" 200 423
[28/Jun/2021 09:18:43] "GET /static/admin/fonts/Roboto-Light-webfont.woff HTTP/1.1" 200 81348
[28/Jun/2021 09:18:43] "GET /static/admin/fonts/Roboto-Regular-webfont.woff HTTP/1.1" 200 80304
[28/Jun/2021 09:18:43] "GET /static/admin/fonts/Roboto-Bold-webfont.woff HTTP/1.1" 200 82564
Not Found: /favicon.ico
[28/Jun/2021 09:18:43] "GET /favicon.ico HTTP/1.1" 404 1975
```
Kemudian anda bisa melihat project ini berjalan dengan mengakses web browser di alamat `http://127.0.0.1:8000/` seperti yang terlihat diatas.

## Pengenalan Fitur Dasari di Django Framework
Setelah `python manage.py runserver` dijalankan, struktur direktori project kita akan seperti ini
```bash
trydjango
├── db.sqlite3
├── manage.py
├── README.md
└── trydjango
    ├── __init__.py
    ├── __pycache__
    │   ├── __init__.cpython-36.pyc
    │   ├── settings.cpython-36.pyc
    │   ├── urls.cpython-36.pyc
    │   └── wsgi.cpython-36.pyc
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```