---
layout: post
title:  "Cara Mudah Menggunakan Django Framework"
date:   2021-06-28 16:38:00 +0800
tags: [Django Framework]
---
## Daftar Isi  
[Persiapan Awal](#persiapan)  
[Virtual Environment](#venv)  
[Membuat Project Django](#membuat_project_django)  
[Pengenalan Fitur Dasar di Django Framework](#fitur_dasar)  
[Setting project anda (settings.py)](#pengaturan)  
[Membuat Aplikasi Pertama Kita](#app_pertama)  
[Mengganti Default Homepage menjadi Homepage Buatan Sendiri](#default_homepage)  
[Django Template](#django_template)  

<a name="persiapan"/>

## Persiapan awal
Tutorial ini cocok diikuti menggunakan `Python 3.6.5` dan `django 2.1.15`.

Sebaiknya menginstall multi-versi dari python menggunakan pyenv agar versi python yang terinstall di system tidak akan terganggu. Lihat artikel Mengatur Instalasi Python Lebih Dari Satu Versi Menggunakan Pyenv di Linux untuk informasi lebih lanjut.

<a name="venv"/>

## Virtual Environment
### Membuat Virtual environment
Buat virtual environment khusus untuk project django 
dengan `python 3.6.5` dan `django 2.1.15`.

Untuk menginstall `python 3.6.5` pada Linux dan Mac, jangan menimpa versi python pada system. Kita bisa menginstall multi-versi python dengan menggunakan tools manajemen bernama pyenv. Disarankan melihat dokumentasi [Cara Menginstall pyenv menggunakan github](https://github.com/pyenv/pyenv#basic-github-checkout){:target="_blank"}.

Untuk membuat virtual environment ketikkan:
```bash
python3 -m venv <nama_virtual_environment>
```
Misalnya nama virtual environmentnya saya namakan `trydjango-dj2115-py365`, maka perintah untuk membuat virutal environment menjadi:
```bash
python3 -m venv trydjango-dj2115-py365
```
Nama virtual environment bisa apa saja. Tapi untuk referensi saya, nama environment saya gunakan `trydjango-dj2115-py365` agar mudah diketahui bahwa virtual environment yang saya buat adalah untuk projek bernama `trydjango` menggunakan versi `django 2.1.15` dan `python 3.6.5`.

### Mengaktifkan Virtual Environment
Untuk menggunakan virtual environment, kita perlu masuk ke dalam direktori virtual environment, dalam hal ini yang kita buat adalah `trydjango-dj2115-py365`, untuk itu ketikkan
```bash
cd trydjango-dj2115-py365
```
Kemudian aktifkan virtual environment dengan mengetikkan
```bash
source bin/activate
```
### Menginstall django di dalam Virtual Environment
Setelah virtual environment diaktifkan, disinilah kita mulai menginstall django
```bash
pip install django==2.1.15
```
Setelah ini, untuk memastikan apakah django sudah terinstall di virtual environment yang kita aktifkan, ketik
```bash
pip freeze
```
dari sini akan terlihat django sudah terinstall:
```bash
❯ pip freeze
Django==2.1.15
pytz==2021.1
```
Virtual Environment Django Framework siap digunakan.

<a name="membuat_project_django"/>

## Membuat Project Django
Setelah virtual environment aktif, kita sudah bisa memulai project kita. setelah masuk ke dalam direktori environment `trydjango-dj2115-py365`, kita buatkan 1 direktori baru untuk menampung project kita. Dalam hal ini saya menamainya `src`, kemudian kita masuk ke dalam direktori tersebut:
```bash
mkdir src
cd src
```
Kemudian buat project baru dengan mengetikkan perintah
```bash
django-admin startproject <nama_project>
```
Misalnya nama project kita namakan `trydjango` maka perintahnya adalah
```bash
django-admin startproject trydjango
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
Django version 2.1.15, using settings 'trydjango.settings'
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
Dapat kita lihat python sudah memiliki apps admin, auth, contenttypes dan sessions yang terintegrasi database dimana terdapat 14 migration yang belum dijalankan. Sebelum lanjut membuat aplikasi nantinya kita harus jalankan terlebih dahulu `python manage.py migrate` atau jika menggunakan python3 maka `python3 manage.py migrate`.

<a name="fitur_dasar"/>

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

<a name="pengaturan"/>

## Setting project anda (settings.py)
File ini terletak di `trydjango/trydjango/settings.py`. Fungsinya adalah sebagai setting dasar pada project Django tertentu yang sedang anda kerjakan, dalam hal ini nama project yang sedang kita kerjakan adalah `trydjango`.
#### Import OS
```python
"""
Django settings for trydjango project.

Generated by 'django-admin startproject' using Django 2.1.15.

For more information on this file, see
https://docs.djangoproject.com/en/2.1/topics/settings/

For the full list of settings and their values, see
https://docs.djangoproject.com/en/2.1/ref/settings/
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
# See https://docs.djangoproject.com/en/2.1/howto/deployment/checklist/

# SECURITY WARNING: keep the secret key used in production secret!
SECRET_KEY = 'disini_secret_key_anda_harus_dirahasiakan_#(l%7_f1=n10c41-kq1x(zp)*b)a5g0h)p+8<'
```
Setiap project django memiliki `secret key` yang berhubungan dengan keamanan pada aplikasi dan anda harus merahasiakannya. Disarankan untuk membuat sedikit perubahan pada secret key dengan menambahkan beberapa karakter.

#### Debuging
```python
# SECURITY WARNING: don't run with debug turned on in production!
DEBUG = True
```
Saat masa develop maka value debug kita atur menjadi `True` sehingga jika ada error saat test running, bisa kelihatan apa errornya. Namun ketika suda final & apikasi web kita sudah live dan bisa diakses online oleh siapa saja, maka anda harus merubahnya menjadi `False`.

#### Allowed Hosts
```python
ALLOWED_HOSTS = []
```
mengijinkan host / PC mana saja yang bisa mengakses aplikasi ini

#### Installed Apps
```python

# Application definition

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',   
]
```
Tempat menampung aplikasi anda. Mulai dari aplikasi bawaan  django, aplikasi eksternal yanga anda tambahkan, maupun aplikasi buatan anda sendiri.

#### Middleware
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
Berhubungan dengan requests dan fitur keamanan yang sudah terinstall di dalam Django.

#### URL Configuration
```python
ROOT_URLCONF = 'trydjango.urls'
```
Menangani URL pada aplikasi Django.

#### Templates
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
Bagian Templates dimana Django melakukan render terhadap template HTML.

#### WSGI Application
```python
WSGI_APPLICATION = 'trydjango.wsgi.application'
```

#### Databases
```python
# Database
# https://docs.djangoproject.com/en/2.1/ref/settings/#databases

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
```
Disini tempat koneksi database. Secara default telah tersambung pada sqlite3 dalam project ini yaitu `trydjango/trydjango/settings.py/db.sqlite3`. Kita bisa juga menggunakan database lain seperti MySql, PostgreSQL, dan lain sebagainya.

#### Password Validator
```python
# Password validation
# https://docs.djangoproject.com/en/2.1/ref/settings/#auth-password-validators

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
Ini untuk memvalidasi apakah password yang kita gunakan sudah sesuai standard yang digunakan saat ini oleh Django.

#### Internationalization
```python
# Internationalization
# https://docs.djangoproject.com/en/2.1/topics/i18n/

LANGUAGE_CODE = 'en-us'

TIME_ZONE = 'UTC'

USE_I18N = True

USE_L10N = True

USE_TZ = True
```
Internationalization seringkali disebut dengan singkatan `i18n`, artinya bahwa terdapat 18 huruf diantara huruf pertama dan terakhir. Internationalization merupakan proses atau prosedur dalam perancangan suatu aplikasi, sehingga memungkinkan penyesuaian atau adaptasi terhadap berbagai bahasa, negara, format penulisan angka maupun pengaturan-pengaturan lainnya yang bersifat spesifik dengan mudah. Dengan kata lain, internationalization merupakan prosedur generalisasi suatu aplikasi.

#### Static files
```python
# Static files (CSS, JavaScript, Images)
# https://docs.djangoproject.com/en/2.1/howto/static-files/

STATIC_URL = '/static/'
```
Tempat dimana django menangani static files seperti CSS, Javascript dan Gambar.

<a name="app_pertama"/>

## Membuat Aplikasi Pertama Kita
### Aplikasi Bawaan Django
Aplikasi kita atau dikenal dengan _apps_, merupakan komponen utama yang menjadi satu kesatuan dalam project yang kita kerjakan. Jika kita kembali pada `settings.py` di bagian *INSTALLED_APPS*, dapat kita lihat sudah terinstal beberapa apps bawaan django. Disini juga dapat kita daftarkan _aplikasi tambahan_ termasuk _aplikasi buatan sendiri_.
```python
# Application definition

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # third party / aplikasi tambahan

    # own app / aplikasi buatan sendiri
    
]
```
#### app admin
Apps bawaan bernama admin, yaitu `django.contrib.admin` dibuat untuk mengelola user menggunakan database. untuk masuk ke aplikasi tersebut kita harus pastikan server lokal telah berjalan dan dengan mengetikkan <http://127.0.0.1:8000/admin> maka aplikasi admin bisa dibuka. Anda akan diminta memasukkan user ID. Bagaimana kita masuk jika belum ada user ID pada database? Disini app selanjutnya berperan dalam membuat user, yaitu _auth_.
#### app auth
Apps bawaan bernama auth, yaitu `django.contrib.auth` berfungsi membuat user ID pertama di aplikasi dengan level super user. Untuk menjalankannya kita hanya perlu mengetikkan
```bash
python3 manage.py createsuperuser
```
Anda akan diminta mengisi profil user seperti pada contoh dibawah:
```bash
Username (leave blank to use 'joenmarz'): jun
Email address: 
Password: 
Password (again): 
Superuser created successfully.
```
### Aplikasi Buatan Anda Sendiri
Untuk membuat app baru di dalam project anda cukup mengetikkan
```bash
python manage.py startapp <AppName>
```
Misalnya nama app kita adalah _products_ maka
```bash
python manage.py startapp products
```
Setelah itu daftarkan apps products ke _INSTALLED_APPS_ pada file `settings.py`
```python
# Application definition

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # third party / aplikasi tambahan

    # own app / aplikasi buatan sendiri
   'products',
]
```
#### Membuat Database Model untuk app anda
kemudian models.py yang ada di direktori Aplikasi, dalam hal ini `trydjango/products/models.py`
```python
from django.db import models

# Create your models here.
class Product(models.Model):
    title       = models.TextField()
    description = models.TextField()
    price       = models.TextField()
```
Buat migrasi untuk model ini dengan mengetikkan `python manage.py makemigrations`
```bash
❯ python manage.py makemigrations
Migrations for 'products':
  products/migrations/0001_initial.py
    - Create model Product
```
Kemudian lanjutkan dengan migrasi dengan mengetikkan `python manage.py migrate`
```bash
❯ python manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, products, sessions
Running migrations:
  Applying products.0001_initial... OK
```
Saat pertama kali running migrate, tidak hanya aplikasi anda saja yang dieksekusi, termasuk aplikasi bawaan django yaitu admin, auth, dll. Dan itu normal. Selanjutnya jika anda melakukan migrate untuk model dan aplikasi baru maupun yang diedit, maka yang muncul hanya model yang baru dibuat. Jadi ingat kedua perintah ini setelah mengedit model, `python manage.py makemigrations` lalu `python manage.py migrate`. Kedua perintah ini akan sering anda gunakan.

Untuk mendaftarkan aplikasi ini pada menu admin, buka file `admin.py` pada folder aplikasi anda. Dalam hal ini `trydjango/products/admin.py`
```python
from django.contrib import admin

# Register your models here.

```
lalu tambahkan model Product di dalamnya
```python
from .models import Product
```
serta register
```python
admin.site.register(Product)
```
pada _admin.py_ akan menjadi seperti ini
```python
from django.contrib import admin

# Register your models here.
from .models import Product

admin.site.register(Product)
```

### Cara Mengubah Database Model untuk app anda
Jika kita ingin menambahkan field pada model database, ataupun untuk mengubah tipe field tersebut bisa saja dilakukan. Untuk referensi field beserta atributnya dapat melihat dokumentasi django tentang [field types](https://docs.djangoproject.com/en/2.1/ref/models/fields/){:target="_blank"}
Model awal:
```python
from django.db import models

# Create your models here.
class Product(models.Model):
    title       = models.TextField()
    description = models.TextField()
    price       = models.TextField()
```
Model setelah diedit dan ditambahkan atribut:
```python
from django.db import models

# Create your models here.
class Product(models.Model):
    title       = models.CharField(max_length=120) # max_length=required
    description = models.TextField(blank=True, null=True) 
    price       = models.DecimalField(decimal_places=2, max_digits=1000)
    summary     = models.TextField(default='produk baru')
    active      = models.BooleanField() # tambahan field
```
Setelah itu jalankan kembali kedua perintah ini setelah mengedit model, `python manage.py makemigrations` lalu `python manage.py migrate`.
```bash
❯ python manage.py makemigrations
You are trying to add a non-nullable field 'active' to product without a default; we can\'t do that (the database needs something to populate existing rows).
Please select a fix:
 1) Provide a one-off default now (will be set on all existing rows with a null value for this column)
 2) Quit, and let me add a default in models.py
Select an option:
```
Disini kita lihat bahwa ketika kita menambahkan 1 field baru dalam hal ini `active`, dan menjalankan makemigrations, django akan menanyakan value yang akan diisi pada field active jika ditambahkan pada existing data yang sebelumnya belum ada field ini. Maka kita tinggal memilih opsi nomor 1, kemudian mengisi value apa yang kita perlukan untuk diisi di semua existing data/record.
```bash
Please enter the default value now, as valid Python
The datetime and django.utils.timezone modules are available, so you can do e.g. timezone.now
Type 'exit' to exit this prompt
>>> True
```
Dalam hal ini karena field active saya buat sebagai BooleanField maka nilainya pasti 1/0 atau True/False. Maka sebagai default telah saya isi dengan nilai `True`.
Untuk field `summary` tidak ditanya lagi oleh Django karena kita sudah menentukan atribut default: `default='produk baru'`

Maka proses makemigrations akan berjalan:
```bash
Migrations for 'products':
  products/migrations/0003_auto_20210709_0937.py
    - Add field active to product
    - Add field summary to product
    - Alter field description on product
    - Alter field price on product
    - Alter field title on product
```
Sampai diatas model sudah diubah dan siap dimigrasi. Lanjutkan dengan proses migrate
```bash
❯ python manage.py migrate       
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, products, sessions
Running migrations:
  Applying products.0003_auto_20210709_0937... OK
```
Sesudah proses ini, model anda telah siap dan database telah berubah sesuai kebutuhan.

### Mengolah data lewat Shell
Pada masa development apliksi, kita bisa juga mengolah database, menambahkan maupun menghapus data dengan menggunakan Shell, yang khusus didesign django. Untuk membuka shell kita perlu mengetikkan perintah `python manage.py shell`
```bash
❯ python manage.py shell
Python 3.6.5 (default, Jun 28 2021, 16:08:02) 
[GCC 10.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
(InteractiveConsole)
>>> 
```
Kita bisa menggunakan perintah bawaan django karena shell ini diperuntukan buat project yang sedang kita kerjakan. Untuk menambahkan data dilakukan perintah berikut:
```bash
>>> from products.models import Product
>>> Product.objects.create(title='Produk Lagi', price=355.50, summary='Produk hebat kembali beredar', active=True)
<Product: Product object (3)>
>>> 
```

<a name="default_homepage"/>

## Mengganti Default Homepage menjadi Homepage Buatan Sendiri
### Membuat View
Pertama-tama kita buat satu app yang bisa kita namakan misalnya `pages`. Untuk cara membuat app dapat melihat referensi topik [Membuat Aplikasi Pertama Kita](#app_pertama).

Untuk membuat view pada app yang kita buat, maka masuk di `pages/views.py`
```python
from django.shortcuts import render

# Create your views here.
```
Kita definisikan fungsi `home_view`
```python
from django.shortcuts import render

# Create your views here.
def home_view():
    return "<h1>Halo Semua..!</h1>"
```
Jika diperhatikan return hanya memberikan string dalam bentuk html, namun itu tidak langsung bisa berfungsi sebagai view html. Agar html bisa terbaca, kita perlu mengimpor fungsi http bawaan django `from django.http import HttpResponse` kemudian menggunakan fungsi tersebut pada string tersebut. Kita juga perlu menambahkan `*args` dan `**kwargs` yang fungsinya untuk membaca _argumen tanpa keyword (*args)_ dan _argumen dengan keyword (**kwargs)_
```python
from django.http import HttpResponse # fungsi HttpResponse ditambahkan
from django.shortcuts import render

# Create your views here.
def home_view(*args, **kwargs): # *args dan **kwargs ditambahkan
    return HttpResponse("<h1>Halo Semua..!</h1>") # menggunakan fungsi HttpResponse pada string
```

### Membuat URL untuk View
Setelah view dibuat, saatnya menampilkannya pada URL supaya saat kita mengetikkan `http://127.0.0.1:8000/pages` maka app pages bisa terbuka. Saat ini belum bisa karena kita belum mendaftarkan URL tersebut.

Cara mendaftarkan URL yaitu kita buka pada `trydjango/urls.py`
```python
"""trydjango URL Configuration

The `urlpatterns` list routes URLs to views. For more information please see:
    https://docs.djangoproject.com/en/2.1/topics/http/urls/
Examples:
Function views
    1. Add an import:  from my_app import views
    2. Add a URL to urlpatterns:  path('', views.home, name='home')
Class-based views
    1. Add an import:  from other_app.views import Home
    2. Add a URL to urlpatterns:  path('', Home.as_view(), name='home')
Including another URLconf
    1. Import the include() function: from django.urls import include, path
    2. Add a URL to urlpatterns:  path('blog/', include('blog.urls'))
"""
from django.contrib import admin
from django.urls import path

urlpatterns = [
    path('admin/', admin.site.urls),
]
```
untuk menambahkan url `home_view` yang kita buat tadi, maka pada `urls.py` kita tambahkan:
```python
from pages.views import home_view    # import view app pages di sini. Jika lebih dari satu view maka pisahkan dengan koma.
from django.contrib import admin
from django.urls import path

urlpatterns = [
    path('', home_view, name='home'),    # tambahkan url pattern di sini
    path('admin/', admin.site.urls),
]
```
Sehingga jika ditesting view ini pada `http://127.0.0.1:8000/` maka url sudah bisa dibuka.

### Menambahkan Request pada View
Kita bisa menambahkan _request_ pada view. Salah satu fungsi dari _request_ adalah kita bisa mengetahui user mana yang login.

Tanpa request view kita terlihat seperti ini:
```python
from django.http import HttpResponse
from django.shortcuts import render

# Create your views here.
def home_view(*args, **kwargs):
    return HttpResponse("<h1>Halo Semua..!</h1>")
```
Dan pada _runserver_ tampilannya hanya seperti ini:
```bash
Performing system checks...

System check identified no issues (0 silenced).
July 11, 2021 - 08:25:35
Django version 2.1.15, using settings 'trydjango.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```
Dengan menambahkan request, kita bisa mengetahui user id mana yang sedang login. Contohnya menambahkan kode `print(request.user)` pada view.
```python
from django.http import HttpResponse
from django.shortcuts import render

# Create your views here.
def home_view(request, *args, **kwargs): # request ditambahkan
    print(request.user) # mengetahui user id yang sedang login
    return HttpResponse("<h1>Halo Semua..!</h1>")
```
Dan ketika kita _runserver_ maka tampilannya akan seperti ini:
```bash
System check identified no issues (0 silenced).
July 11, 2021 - 08:30:10
Django version 2.1.15, using settings 'trydjango.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
joenmarz
[11/Jul/2021 08:30:23] "GET / HTTP/1.1" 200 19
```
Bisa terlihat user ID saya `joenmarz` sedang aktif saat ini. Dan ini adalah salah satu contoh menangani views dengan benar.

<a name="django_template"/>

## Django Template
Tentunya kita tidak akan melakukan render string atas kode html yang kita buat seperti contoh dibawah:
```python
...
def home_view(request, *args, **kwargs):
    print(request.user)
    return HttpResponse("<h1>Halo Semua..!</h1> <p>dan sebagainya...</p>") # tidak direkomendasikan :)
```
Kita membutuhkan template html yang dapat kita render dari views. Hal ini menjadi sangat efisien dimana kita tidak perlu mengetikkan kode html berulang-ulang untuk template seperti navbar, sidebar menu dan sejenisnya. Ini hanyalah beberapa contoh. Mari kita pelajari tentang Django Template.

Jadi untuk `return HttpResponse(arguments)` kita ganti menjadi
```python
from django.http import HttpResponse
from django.shortcuts import render

# Create your views here.
def home_view(request, *args, **kwargs):
    print(request.user)
    # return HttpResponse("<h1>Halo Semua..!</h1>")
    return render(request, "home.html", {}) # return render(request, "page.html", context)
```
Jika kita jalankan tentunya akan error, karena file `home.html` belum kita buat. Untuk itu mari kita buat folder yang bisa kita namakan apa saja, dalam hal ini saya namakan `templates` yang kita buat di dalam folder `src`, menjadi `trydjango/src/templates`.