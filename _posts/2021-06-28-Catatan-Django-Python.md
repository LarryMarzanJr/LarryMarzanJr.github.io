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

## Pengenalan Fitur Dasar di Django Framework
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
Mari kita bahas beberapa fitur dasar yang ada didalamnya. Karena kita membuat project dengan nama `trydjango`, maka struktur direktori akan banyak muncul dengan nama direktori ini. Nama project yang anda gunakan bisa saja berbeda, sesuai dengan kebutuhan.
### Setting project anda (settings.py)
File ini terletak di `trydjango/trydjango/settings.py`. Fungsinya adalah sebagai setting dasar pada project Django tertentu yang sedang anda kerjakan, dalam hal ini nama project yang sedang kita kerjakan adalah `trydjango`.
#### Import OS
```python
"""
Django settings for trydjango project.

Generated by 'django-admin startproject' using Django 2.0.7.

For more information on this file, see
https://docs.djangoproject.com/en/2.0/topics/settings/

For the full list of settings and their values, see
https://docs.djangoproject.com/en/2.0/ref/settings/
"""

import os
```
Dengan `import os` maka Django mengenali semua jenis Operating System yang anda gunakan baik itu Linux, Windows maupun Mac.
#### BASE_DIR
```python
# Build paths inside the project like this: os.path.join(BASE_DIR, ...)
BASE_DIR = os.path.dirname(os.path.dirname(os.path.abspath(__file__)))
```
Variabel `BASE_DIR` dengan isinya, mengidentifikasi letak dari file `manage.py` namun lebih utama lagi lokasi atau path direktori sebelum masuk ke direktori project kita yang dalam hal ini saya namakan `trydjango`.
#### Secret Key
```python

# Quick-start development settings - unsuitable for production
# See https://docs.djangoproject.com/en/2.0/howto/deployment/checklist/

# SECURITY WARNING: keep the secret key used in production secret!
SECRET_KEY = 'disini_secret_key_anda_harus_dirahasiakan_#(l%7_f1=n10c41-kq1x(zp)*b)a5g0h)p+8<'
```
Setiap project django memiliki `secret key` yang berhubungan dengan keamanan pada aplikasi dan anda harus merahasiakannya. Disarankan untuk membuat sedikit perubahan pada secret key dengan menambahkan beberapa karakter.

### Debuging
```python
# SECURITY WARNING: don't run with debug turned on in production!
DEBUG = True
```
Saat masa develop maka value debug kita atur menjadi `True` sehingga jika ada error saat test running, bisa kelihatan apa errornya. Namun ketika suda final & apikasi web kita sudah live dan bisa diakses online oleh siapa saja, maka anda harus merubahnya menjadi `False`.

```python
ALLOWED_HOSTS = []
```
```python

# Application definition

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # external apps

    # own app
    
]
```
```python
MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]
```
```python
ROOT_URLCONF = 'trydjango.urls'
```
```python
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
```
```python
WSGI_APPLICATION = 'trydjango.wsgi.application'


# Database
# https://docs.djangoproject.com/en/2.0/ref/settings/#databases

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
```
```python

# Password validation
# https://docs.djangoproject.com/en/2.0/ref/settings/#auth-password-validators

AUTH_PASSWORD_VALIDATORS = [
    {
        'NAME': 'django.contrib.auth.password_validation.UserAttributeSimilarityValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.MinimumLengthValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.CommonPasswordValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.NumericPasswordValidator',
    },
]
```
```python

# Internationalization
# https://docs.djangoproject.com/en/2.0/topics/i18n/

LANGUAGE_CODE = 'en-us'

TIME_ZONE = 'UTC'

USE_I18N = True

USE_L10N = True

USE_TZ = True
```
```python

# Static files (CSS, JavaScript, Images)
# https://docs.djangoproject.com/en/2.0/howto/static-files/

STATIC_URL = '/static/'
```