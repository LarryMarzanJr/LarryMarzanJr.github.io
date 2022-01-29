---
layout: post
title:  "Instalasi Yii 2.0 Framework"
date:   2015-10-23 00:00:00 +0800
categories: [post, php]
---

![Yii2](https://1.bp.blogspot.com/-htYx9pASWbQ/VirsysuRT1I/AAAAAAAAFXI/mLEuJ8GfMr8/s1600/yii2framework-logo.jpg)

Saat ini saya akan memperlihatkan bagaimana melakukan instalasi Yii 2.0 Framework.

Yii 2.0 memiliki dua macam Template untuk digunakan yaitu Basic dan Advanced. Salah satu perbedaan yang dapat dilihat dari kedua template tersebut yaitu pada Basic hanya menggunakan 1 layer menu untuk semua pengguna, sedangkan pada Advanced sudah menggunakan 2 layer menu atau lebih dikenal dengan Frontend dan Backend.

Penggunaan dari setiap template ini bergantung pada masing-masing kebutuhan end-user. Terdapat dua alternatif dalam melakukan instalasi template. Pertama dengan mendownload langsung template yang sudah disediakan oleh Yii Framework. Atau pilihan kedua yaitu dengan menggunakan Composer. Nah, mari kita bahas kedua cara tersebut.
## Instalasi menggunakan Template
Pertama-tama kita perlu mendownload template yang kita butuhkan:
1. Untuk pengguna Yii2 Basic Template - [download](https://github.com/yiisoft/yii2/releases/download/2.0.6/yii-basic-app-2.0.6.tgz){:target="_blank"}
2. Untuk pengguna Yii2 Advanced Template - [download](https://github.com/yiisoft/yii2/releases/download/2.0.6/yii-advanced-app-2.0.6.tgz){:target="_blank"}

# Yii2 Basic Template
Extract template yang sudah berhasil didownload dan akan menghasilkan files dalam satu folder yang bernama basic. Folder tersebut dapat di-rename sesuai keinginan/kebutuhan.

Sebelumnya saya asumsikan anda sudah memiliki webserver lokal seperti XAMPP (atau sejenisnya: WAMP, LAMP, MAMP, dsb.). Jika belum silahkan lihat panduan instalasi XAMPP disini.

Dalam hal ini saya menggunakan OS Windows sehingga folder Webserver pada XAMPP ada di `c:\xampp\htdocs`. Copy dan Paste template basic ke dalam folder tersebut.

Untuk mengakses template Basic gunakan URL berikut:
```
http://localhost/basic/web/index.php
```

Namun sebelum anda dapat mengaksesnya, terlebih dahulu perlu dilakukan pengisian `cookieValidationKey`. Jika tidak dilakukan maka aplikasinya tidak akan jalan, dan muncul error seperti di bawah:

![Yii2 Error](https://1.bp.blogspot.com/-tSzB6EfyQiQ/VjiDAL0kSxI/AAAAAAAAFb0/FTs_1eltQGA/s640/basic_configure_cookieValidationKey.png)

Untuk itu kita harus melakukan setting dengan cara masuk ke file web.php yang ada di folder project Basic anda:
```
/basic/config/web.php
```

didalamnya kita tambahkan cookieValidationKey:
```php
$config = [
...
     'components'  = [
          'request' = [
               // input cookieValidationKey disini, misalnya 'yii2belajar' :)                    'cookieValidationKey' => 'yii2belajar',
          ],
          ...
     ],
];
```
Instalasi Basic Template Yii 2.0 selesai. Silahkan dicoba akses kembali dengan URL http://localhost/basic/web/index.php dan tampilanya akan seperti ini:

![Yii2 Basic](https://4.bp.blogspot.com/--ggOfefrRm4/VilVaZpPZNI/AAAAAAAAFUI/wkscbuXwBVM/s640/tampilan_awal_frontend.png)

# Yii2 Advanced Template
Extract template yang sudah berhasil didownload dan akan menghasilkan files dalam satu folder yang bernama advanced. Folder tersebut dapat di-rename sesuai keinginan/kebutuhan.

Sebelumnya saya asumsikan anda sudah memiliki webserver lokal seperti XAMPP (atau sejenisnya: WAMP, LAMP, MAMP, dsb.). Jika belum silahkan [download XAMPP webserver disini](https://www.apachefriends.org/download.html){:target="_blank"}.

Dalam hal ini saya menggunakan Sistem Operasi Windows sehingga folder Webserver pada XAMPP ada di `c:\xampp\htdocs`. Copy dan Paste template advanced ke dalam folder tersebut.

Lakukan inisiasi pada template ini. Caranya dengan masuk ke command prompt pada direktori template anda dan menjalankan perintah berikut:
```
php init
```
![php init](https://3.bp.blogspot.com/-XHCbIJhWU4w/VilUo6lEIzI/AAAAAAAAFTs/jOX5L3WgR80/s1600/php_init.png)

Tips:
Folder Instalasi PHP dapat terletak berbeda-beda tergantung Webserver lokal maupun Sistem Operasi yang kita gunakan, sehingga terkadang perintah php init tidak serta-merta dapat langsung dieksekusi seperti diatas. Pada Sistem Operasi Windows dengan menggunakan Webserver XAMPP, folder hasil instalasi php terdapat di `c:\xampp\php` sehingga saat menjalankan perintah php harus diketik dengan folder tempat php.exe berasal. Perintahnya berubah menjadi: `c:\xampp\php\php init` Hal ini sangat tidak efisien ketika kita harus menghafal folder php tersebut. Namun dengan sedikit konfigurasi mudah anda dapat mengubahnya. Silahkan lihat tutorialnya di sini: [Setting Path Environment Variable](#){:target="_blank"}

Selanjutnya pilih Development (0) dan konfirmasi (y)

![konfirmasi php init](https://2.bp.blogspot.com/-s6h3CetynpY/VilVXawxDlI/AAAAAAAAFT0/GE39JbpZwAc/s1600/choose_0_development.png)

Template Yii2 Advanced sudah siap digunakan. Perlu diingat template ini memiliki dua layer aplikasi terpisah yang dapat diakses oleh end-user yaitu Frontend dan Backend. Untuk mengakses layer Frontend urlnya adalah:
```
localhost/advanced/frontend/web/index.php
 ```
![tampilan Frontend](https://4.bp.blogspot.com/--ggOfefrRm4/VilVaZpPZNI/AAAAAAAAFUI/wkscbuXwBVM/s640/tampilan_awal_frontend.png)

*tampilan awal Frontend*

Untuk mengakses layer Backend urlnya adalah:
```
localhost/advanced/backend/web/index.php
```
![tampilan Backend](https://1.bp.blogspot.com/-KcvhW0Ty-XQ/VilVaE8bl9I/AAAAAAAAFUE/wnbiyZ4IfEE/s640/tampilan_awal_backend.png)

*tampilan awal backend*

## Instalasi menggunakan Composer

Para developer PHP tentunya sudah tidak asing lagi dengan Composer. Namun jika kita belum pernah menggunakan Composer sebelumnya, silahkan pelajari [Cara Mudah Menggunakan Composer](https://larrymarzanjr.gitlab.io/php/package manager/2015/10/23/Cara-Mudah-Menggunakan-Composer.html){:target="_blank"}. Setelah Composer terinstall silahkan melakukan instalasi `Composer Asset Plugin`:
```
php composer.phar global require "fxp/composer-asset-plugin:~1.0.3"
```

### Yii2 Basic Template Menggunakan Composer
Untuk menginstall basic template menggunakan composer cukup mudah, yaitu dengan mengetikkan perintah:
```
php composer.phar create-project yiisoft/yii2-app-basic basic 2.0.6
```
Selanjutnya lakukan pengisian cookieValidationKey, caranya sama seperti diatas (setelah extract template Basic).

Instalasi Basic Template menggunaka composer selesai!

### Yii2 Advanced Template Menggunakan Composer
Untuk menginstall advanced template menggunakan composer juga cukup mudah, yaitu dengan mengetikkan perintah:
```
php composer.phar create-project yiisoft/yii2-app-advanced advanced 2.0.6
```
Selanjutnya lakukan inisiasi (php init) sama seperti di atas (setelah extract template Advanced).

Sampai disini cara menginstal Yii 2.0 framework sudah selesai. Semoga Bermanfaat.