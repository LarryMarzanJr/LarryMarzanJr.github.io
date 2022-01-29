---
layout: post
title:  "Membuat Aplikasi CRUD Secara Otomatis Menggunakan Gii di Yii 2.0"
date:   2018-03-07 00:00:00 +0800
categories: [post, php]
---

![Yii2 Gii](https://2.bp.blogspot.com/-crV7CGs1oK4/VitThGhb57I/AAAAAAAAFXg/zcNtSgzCmq4/s640/Gii.png){:target="_blank"}

Yii memiliki tool untuk membuat Model, Controller, Form, Module, bahkan aplikasi CRUD secara otomatis. Keuntungan membuat aplikasi berbasis framework salah satunya yaitu adanya fitur otomasi untuk membuat aplikasi dasar CRUD (Create-Read-Update-Delete). Aplikasi CRUD telah disempurnakan dari sebelumnya. Salah satu contoh yaitu jika kita menyusun database-model (tabel) yang memiliki field yang berproperty `enum`, maka pada view nantinya input property yang dihasilkan bukan lagi `textInput`, melainkan dropdown menu yang sudah terkoneksi model. Dan masih ada beberapa fitur lagi yang ditambahkan.

Oke mari kita mulai!

Pertama-tama tentunya Template Yii2.0 sudah harus ter-install. Mari kita gunakan template Yii2.0 advance. Lihat Instalasi Yii 2.0 Framework.


Selanjutnya kita membutuhkan Model database untuk bekerja dengan tools Gii CRUD Generator ini. Sebagai contoh mari kita buat database di MySQL dengan nama yii2belajar dan tambahkan tabel tambah_file sbb:
```
CREATE TABLE IF NOT EXISTS `tambah_file` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `file_upload` int(11) NOT NULL,
  `avatar_id` int(11) NOT NULL,
  `user_id` int(11) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 AUTO_INCREMENT=1 ;
```
Koneksikan database yang anda buat. Untuk cara Koneksi database di Yii2, klik disini

Pada template Advanced anda dapat memilih membuat/menempatkan aplikasi CRUD anda pada `frontend` maupun `backend`. Pada kesempatan ini mari kita gunakan frontend. Buka Gii Tool di pada template advance frontend anda dengan mengetikkan sbb:
```
http://localhost/advanced/frontend/web/index.php?r=gii
```
Untuk membuat CRUD kita harus membuat Model terlebih dahulu, selanjutnya untuk Controller dan View akan generate otomatis pada saat kita membuat CRUD. Pada *Model Generator* klik Start.
![Model Generator](https://1.bp.blogspot.com/-yY1MsSG49JI/VjhNRpY7uoI/AAAAAAAAFZw/lzZ2OPF6_oc/s1600/model_generator.png){:target="_blank"}

Tambahkan nama tabel pada `Table Name` sesuai yang kita buat sebelumnya yaitu:
```
tambah_file
```
Beri nama model sesuai tabel pada `Model Class`. Standarisasi penamaan model yaitu selalu diawali dengan huruf kapital. Saran saya untuk memudahkan penamaan, jika nama yang digunakan lebih dari satu suku kata maka sebaiknya setiap awal kata diawali dengan huruf kapital. Dalam hal ini nama tabel tambah_file maka nama model adalah:
```
TambahFile
```
Namespace pada template advance disesuaikan dengan layer yang kita gunakan. Apabila kita menggunakan layer *frontend* maka namespace menjadi `frontend\models` atau jika *backend* maka menjadi `backend\models`. (Pada advance template sebaiknya jangan menggunakan menggunakan app\models). Saat ini kita menggunakan layer frontend, jadi namespacenya menjadi:
```
frontend\models
```
![Penamaan model](https://3.bp.blogspot.com/-ewyOy2Zx8mc/VjhS4UIAeVI/AAAAAAAAFaQ/0P-oHYJY8_o/s320/penamaan_model.png){:target="_blank"}

Setelah selesai penamaannya, klik *Preview*, 
![Model Preview](https://2.bp.blogspot.com/-fmCFoGglGJ8/VjhTIIgRSVI/AAAAAAAAFaY/FvdD40MJCqo/s1600/model_preview.png){:target="_blank"}

kemudian *Generate*. Dan akan muncul tampilan seperti di bawah, dimana Model anda telah berhasil dibuat.
![Model Generate](https://1.bp.blogspot.com/-F-I2EL1bQZw/VjhTIcY_DmI/AAAAAAAAFak/kDWhg7R9LqU/s1600/model_generate.png){:target="_blank"}

Model telah selesai dibuat! Nah sekarang tinggal membuat CRUD. Pada CRUD Generator klik *Start*.
![CRUD Generator](https://1.bp.blogspot.com/-94nmRUPk7YU/VjhNYnggjlI/AAAAAAAAFaA/XZZVMzYWCHI/s1600/CRUD_generator.png){:target="_blank"}

Pada `Model Class` diisi dengan
```
frontend\models\TambahFile
```
Pada `Search Model Class` diisi dengan
```
frontend\models\TambahFileSearch
```
Penamaan Controller selalu ditambahkan/disambung dengan kata *Controller* contoh: `NamaController`. Untuk itu nama controller saat ini menjadi `TambahFileController`. Isi pada Controller Class dengan:
```
frontend\controllers\TambahFileController 
```
![Penamaan pada CRUD](https://2.bp.blogspot.com/-OEiuM9XT1nA/VjhYbt7i_kI/AAAAAAAAFaw/L0O7v6vwUqU/s1600/penamaan_pada_CRUD.png){:target="_blank"}

Setelah selesai dengan penamaan ini, klik *Preview*. Maka akan tampil beberapa form yang nantinya akan di-generate, yaitu modelSearch, Controller, serta beberapa view yang nantinya kan digunakan end-user (pengguna program anda) dalam berinteraksi dengan aplikasi CRUD yang dibuat.
![Preview CRUD](https://1.bp.blogspot.com/-QaPkv5dO9XI/VjhYwAH3s_I/AAAAAAAAFa4/lw6uhdgU61k/s1600/CRUD_preview.png){:target="_blank"}

Pastikan semua form sudah dicentang, jika tidak form yang tidak dicentang tidak akan muncul. Sesudah itu klik *Generate*. Sehingga akan muncul tampilan seperti di bawah:
![CRUD Generate](https://2.bp.blogspot.com/-SkStHYM51vQ/VjhaPqnMKfI/AAAAAAAAFbE/UCKwYdNidLw/s1600/CRUD_generate.png){:target="_blank"}

Aplikasi CRUD anda telah selesai! Untuk mengakses URL aplikasi ini, tinggal mengetikkan:
```
http://localhost/advanced/frontend/web/index.php?r=tambah-file
```
Jika sebelumnya anda membuat Model dan CRUD pada layer backend, maka URLnya adalah:
```
http://localhost/advanced/backtend/web/index.php?r=tambah-file
```
Jika anda ingin melakukan perubahan pada codenya, folder file terdapat di sini:

Untuk frontend:
```
models:
advanced/frontend/models
controllers:
advanced/frontend/controllers
view
advanced/frontend/views
```
Untuk backend:
```
models:
advanced/backend/models
controllers:
advanced/backend/controllers
view
advanced/backend/views
```
Selesai! Semoga bermanfaat & Selamat mencoba.