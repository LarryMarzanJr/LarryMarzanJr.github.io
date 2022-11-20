# Find and Replace Karakter Di Vim


<!--more-->
Artikel ini menggambarkan cara melakukan find and replace text di vim.

Secara umum perintah yang digunakan sebagai berikut:
```
:[range]s/{pattern}/{string}/[flags] [count]
```

Perintah diatas mencari setiap line pada [range] dengan kata kunci pada {pattern}, kemudian
menggantinya dengan {string}
[count] merupakan bilangan positif yang menghitung berapa kali perintah ini dieksekusi.
Jika [range] dan [count] tidak digunakan maka hanya baris yang sedang kita edit yang akan
berpengaruh. Baris yang diedit yaitu dimana kursor berada.

Contoh sederhana, misal kita akan mencari kata `foo` dan untuk hasil pencarian pertama kita
menggantinya dengan `bar`, maka kita gunakan perintah:
```
:s/foo/bar/
```
Untuk melakukan replace pada keseluruhan baris yang dengan kondisi yang sama, kita tambahkan
flag g:
```
:s/foo/bar/g
```
Jika dengan kondisi yang sama anda ingin melakukan replace ke seluruh isi file, tambahkan
karakter % yang berfungsi sebagai range.
```
:%s/foo/bar/g
```
Jika pada {string} kita kosongkan, maka semua hasil pencarian akan dihapus.
Pada contoh berikut akan menghapus semua {pattern} yang mengandung string 'foo' pada satu baris:
```
:s/foo//g
```
Disamping menggunakan karakter garis miring (/) sebagai pemisah, kita juga dapat menggunakan karakter
non-alphanumeric lain sebagai pemisah string. Ini berfungsi jika disaat kita sedang melakukan pencarian
yang mengandung karakter '/', seperti contoh berikut kita akan mencari 'foo/' dan menggantinya
dengan 'bar':
```
:s|foo/|bar|
```
Untuk mengkonfirmasi tiap perubahan, gunakan flag c seperti contoh:
```
:s/foo/bar/gc
```
```
replace with bar (y/n/a/q/l/^E/^Y)?
```
Tekan y untuk menimpa hasil atau l untuk menimpa dan selesai. Tekan n untuk mengabaikan hasil pencarian
dan q atau Esc untuk menghentikan pencarian. Pilihan a atau 'all' mencari dan mengganti semua
hasil pencarian yang cocok dengan string yang disediakan. Untuk scroll kebawah CTRL+Y (^Y) dan CTRL+E
(^E) untuk scroll ke atas.

