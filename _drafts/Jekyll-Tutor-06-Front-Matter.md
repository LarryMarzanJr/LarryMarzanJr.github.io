---
layout: page
tags: [Jekyll]
categories: [Static Site Generator]
date: 2020-09-24 12:25:01 +0800
#excerpt: ''
#image: 'BASEURL/assets/blog/img/.png .jpg'
#description: 
#permalink: 
title: 'Front Matter'
pelajaran: 'Pelajaran 6'
author: 'Larry Marzan Jr.'
---
{% youtube "https://www.youtube.com/watch?v=jwSBE1EIevA" %}

Front Matter adalah tempat kita menyimpan informasi tentang seluruh laman di situs kita.

Jadi seluruh laman di website Jekyll kita akan memiliki *front matter*. Pada dasarnya *front matter* akan menampung informasi tentang laman itu sendiri, seperti judul, tanggal pembuatan laman, atau mungkin penulis laman. Jadi *front matter* bisa memberikan kita informasi tentang setiap halaman.
```yaml
---
layout: post
title: "Welcome To Jekyll!"
date: 2020-09-24 12:25:01 +0800
categories: jekyll update
---
```
<!-- 
Catatan tambahan:
Sekarang mari kita buka folder _posts dan di dalamnya kita memiliki 1 postingan blog.
Anda akan melihat di bawah sini kita memiliki konten dari sebuah blog. Isi dari konten ini ditulis dalam bentuk markdown.

Namun jika kita lihat di bagian paling atas dari file ini kita memiliki beberapa informasi khusus yang ditulis dengan format yang berbeda. Tulisanya dipisahkan dengan tiga garis datar di bagian atas dan bawah dari penulisan,
dan ini sebenarnya adalah front matter dari sebuah postingan blog yang dimaksud tadi.

Jadi seperti saya bilang di awal, front matter adalah informasi dari postingan blog kita, dalam hal ini kita mendefinisikan layout, judul dari postingan (title), tanggal posting (date),

Front matter bisa dipilih cara penulisannya, mengunakan YAML atau JSON.

Jadi pada dasarnya front matter hanya berisi variabel. Jadi kita punya key nya, kemudian disini kita memiliki nilai atau isi dari variabel tersebut.

Jadi saya akan mencontohkan cara menggunakannya.

Di sini kita memiliki tampilan dari postingan blog yang sudah jadi melalui browser web.

Saya memiliki homepage, dan disini adalah 1 postingan blog yaitu "Welcome To Jekyll".
Jadi postingan ini menggunakan variable title untuk menampilkan judul dari postingan blog. Jadi kalau saya ke bagian title dan mengubah nya, saya dapat mengetikkan "Ini Judul Baru".

Dan di sisi websitenya disini, titlenya akan ter update, jadi judulnya tadinya "Welcome To Jekyll" telah berubah menjadi "Ini Judul Baru".

Saya juga bisa memperbaharui variable date, jadi tanggal postingan blog bisa disesuaikan menjadi "tanggal sekian", jadi di bagian postingan tanggal juga akan berubah sesuai pengaturan tadi.

Jadi tema dari Jekyll yang kita gunakan itu mengambil informasi dari front matter ini, dan menggunakannya untuk menampilkan postingan blog di website kita.

Jadi dengan mengubah front matter dari sebuah laman, anda dapat mengubah apa yang akan ditampilkan pada website.

Front matter juga berperan dalam menampilkan URL yang akan kita klik saat akan menampilkan isi dari postingan blog. Jadi jika saya klik di judul iink ini maka akan muncul URL seperti ini. Jadi URL dari laman sebenarnya menggunakan tanggal dan categories untuk menampilkan postingan. Jadi bisa terlihat dimana sebenarnya artilkel tersimpan. Jadi jika saya mengubah kategori ini misalnya.

Dan sekaran ketika saya kembali ke home dan klik kembali postingan, maka perhatikan perubahan link di atas ini, sudah disesuaikan dengan kategori yang kita rubah tadi.
 -->