# Menghilangkan URL /public pada project Laravel 10 anda


# Menghilangkan URL /public pada project Laravel 10 
Secara default, project Laravel yang kita buat diakses dengan alamat `http://localhost/project-anda/public/`. Untuk menghilangkan `/public` pada URL tersebut kita perlu menambahkan 2 file di root folder project yaitu `.htaccess` dan `server.php`.

## Membuat file .htaccess
File `.htaccess` yang dibuat pada root folder project diisi dengan konfigurasi sebagai
berikut
```htaccess
IfModule mod_rewrite.c>
    <IfModule mod_negotiation.c>
        Options -MultiViews
    </IfModule>

    RewriteEngine On

    RewriteCond %{REQUEST_FILENAME} -d [OR]
    RewriteCond %{REQUEST_FILENAME} -f
    RewriteRule ^ ^$1 [N]

    RewriteCond %{REQUEST_URI} (\.\w+$) [NC]
    RewriteRule ^(.*)$ public/$1 

    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^ server.php
</IfModule>
```

## Membuat file server.php
File `server.php` yang dibuat pada root folder project diisi dengan konfigurasi sebagai
berikut
```php
<?php

/**
 * Laravel - A PHP Framework For Web Artisans
 *
 * @package  Laravel
 * @author   Taylor Otwell <taylor@laravel.com>
 */

$uri = urldecode(
    parse_url($_SERVER['REQUEST_URI'], PHP_URL_PATH)
);

// This file allows us to emulate Apache's "mod_rewrite" functionality from the
// built-in PHP web server. This provides a convenient way to test a Laravel
// application without having installed a "real" web server software here.
if ($uri !== '/' && file_exists(__DIR__.'/public'.$uri)) {
    return false;
}

require_once __DIR__.'/public/index.php';
```
Kini URL project Laravel 10 anda dapat diakses dengan `http://localhost/project-anda/`


## Referensi
[Youtube tentang How can I remove "/public" from a Laravel 10 / Laravel 9 application using
.htaccess?](https://www.youtube.com/watch?v=Cc2i8Vi0cIw)

[Github rajputrj tentang
laravel10-server.js-.htaccess-file-code](https://github.com/rajputrj/laravel10-server.js-.htaccess-file-code/blob/main/server.js%20and%20.htaccess%20file%20code)

