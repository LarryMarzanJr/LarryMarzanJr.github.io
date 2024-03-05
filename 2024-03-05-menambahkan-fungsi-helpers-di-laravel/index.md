# Menambahkan Fungsi Helpers di Laravel


# Menambahkan Fungsi Helpers di Laravel

## Membuat file helpers.php

Secara default, Laravel sudah memiliki fungsi / helper yang disediakan untuk kita gunakan. Namun ada kalanya kita membutuhkan custom helper buatan sendiri untuk digunakan secara berulang.

Cara menambahkan helpers custom yaitu dengan membuat direktori dan file `Helpers/helpers.php` yang akan kita taruh pada project directory kita di `app/Http/`
```bash
mkdir app/Http/Helpers/helpers.php
```
Di dalam file helpers tersebut kita bisa menambahkan fungsi yang kita butuhkan
```php
<?php

// tambahkan fungsi anda di sini

```

## Mendaftarkan File helpers.php di composer.json
Sebelum helpers bisa kita gunakan, kita perlu mendaftarkan file helpers.php pada file `composer.json` kita perlu mendaftarkan file helpers.php agar dapat digunakan. Tambahkan pada bagian autoload:
```json
"autoload": {
        ...

        "files": [
            "app/Http/Helpers/helpers.php"
        ],
    },
```
Setelah ditambahkan, kita perlu melakukan dump autoload pada composer, baru helpers bisa berfungsi.
```bash
composer dump autoload
```

## Referensi

`...`
