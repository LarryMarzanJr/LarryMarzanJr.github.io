# Koneksi Database MySQL pada Yii 2.0


![koneksi MySQL Yii2](https://3.bp.blogspot.com/-iN4_R6_BhJc/VjhkjBnFz2I/AAAAAAAAFbU/CeopLB5ezzs/s1600/mysql_connect_yii.png)

Pertama-tama kita perlu membuat Database pada MySQL lewat aplikasi database manager `phpmyadmin`. Jika anda menginstal Paket Bundle Webserver lokal seperti XAMPP atau sejenisnya, maka aplikasi phpmyadmin sudah termasuk didalamnya.

Buka phpmyadmin pada web-browser anda dengan mengetikkan:
```
http://localhost/phpmyadmin
```
Klik pada Tab Database. Beri nama database anda mis. `yii2belajar` kemudian jangan lupa set collation menjadi `utf8_general_ci`. Setelah itu klik Create.

![create database](https://4.bp.blogspot.com/-_34vxdTYTWo/VjhyWiEZ3FI/AAAAAAAAFbk/jvRzG_nXD_0/s1600/phpmyadmin_create_database.png)

Database anda sudah jadi! Nah sekarang tinggal koneksi ke Yii 2.0 Template. Untuk setting inisiasi / instalasi Template Yii 2.0 dapat dilihat [disini](https://larrymarzanjr.gitlab.io/php/yii2framework/windows/composer/webserver/2015/10/22/Instalasi-Yii-2.0-Framework.html){:target="_blank"}.

Pada dasarnya script koneksi sudah ada di dalam file konfigurasi. Yang kita perlukan hanya mengganti nama databasenya, sesuai dengan nama database yang kita buat.

Template Yii2.0 Basic kita membuka file konfigurasi `db.php` yang terdapat di:
```
/basic/config/db.php
```
Didalamnya terdapat script koneksi ke database sebagai berikut:
```php
<?php
return [
    'class' => 'yii\db\Connection',
    // ganti nama database pada dbname sesuai dengan nama db yang kita buat diatas
    'dsn' => 'mysql:host=localhost;dbname=yii2belajar',
    'username' => 'root',
    // password Webserver Lokal kita. Jika tidak ada, dikosongkan saja
    'password' => '',
    'charset' => 'utf8',
];
```
Koneksi database untuk Basic Template Yii 2.0 selesai!


Sedangkan pada Template Yii2.0 Advanced file konfigurasinya `main-local.php` yang terdapat di:
```
/advanced/common/config/main-local.php
```
 Script koneksinya sebagai berikut:
```php
<?php
return [
    'components' => [
        'db' => [
            'class' => 'yii\db\Connection',
            // ganti nama database pada dbname sesuai dengan nama db yang kita buat diatas
            'dsn' => 'mysql:host=localhost;dbname=yii2belajar',
            'username' => 'root',
            // password Webserver Lokal kita. Jika tidak ada, dikosongkan saja
            'password' => '',
            'charset' => 'utf8',
        ],
... // lain-lain
    ],
];
```

Koneksi database untuk Basic Template Yii 2.0 selesai!

Bagaimana? Semudah "mencolokkan kabel" bukan? Semoga bermanfaat!


