# Mengembalikan Folder Vendor Di Laravel

## Bagaimana Memperbaiki hilangnya folder vendor di project Laravel anda?
Ketika kita melakukan clone terhadap Project Laravel dari Git, selalu folder `vendor` akan
hilang karena terdaftar di file .gitignore pada saat developer mengupload projectnya,
sehingga kita perlu re-generate folder vendor tersebut menggunakan Composer.
 

## Regenerate vendor folder
Jalankan update composer di dalam project yang telah didownload, agar composer akan menarik
semua package yang terdaftar di composer.json project tersebut dan mendownloadnya ke dalam
folder vendor. Gunakan perintah berikut
```bash
composer update
```
Dalam kebanyakan kasus, update composer ini akan me-regenerate folder vendor dan file
autoload.php

Secara alternatif, kita bisa me-regenerate autoload.php menggunakan perintah
```bash
composer dump-autoload
```

Setelah itu kita bisa memeriksa apakah project laravel tersebut sudah berjalan normal.

## Referensi
[Bobcares.com tentang Laravel Vendor Folder Missing](https://bobcares.com/blog/laravel-vendor-folder-missing/)

