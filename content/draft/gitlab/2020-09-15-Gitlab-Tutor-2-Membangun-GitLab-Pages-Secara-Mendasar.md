---
layout: post
title:  "Membangun GitLab Pages Secara Mendasar"
date:   2020-09-15 00:34:00 +0800
categories: gitlab
---

Sebelum mulai membuatnya, anda perlu [mengenal apa itu GitLab Pages](#){:target="_blank"}. Dan jika belum punya anda dapat [membuat Akun GitLab](https://gitlab.com/users/sign_up){:target="_blank"}.

## Membuat Repositori

Setelah membuat Pada laman [GitLab](https://gitlab.com){:target="_blank"} klik di kanan atas simbol + untuk dan pilih *New Repository*

Pada *Repository Name* tuliskan nama Repositori. Untuk pendeteksian page pada GitLab secara otomatis disarankan untuk membuat `nama_repository.gitlab.io`

*Description* menerangkan tentang Repositori anda, tetapi ini hanyalah kolom opsional.

*Visibility* diatur sebagai *Public* jika anda ingin ada kontributor lainnya di masa yang akan datang, dan set *Private* jika hanya anda atau sesama anggota yang bisa melihat repositori ini.

Untuk *inisiasi Repositori*, tambahkan beberapa file dan lisensi:
- `Add a README file` Untuk menambahkan file Readme di awal terbentuknya Repositori.
- `Add .gitignore` Agar pada saat upload / sync program secara remote, direktori .gitignore tidak akan terupload atau dikecualikan dari proses sinkronisasi git.
- `Choose a license`, Anda akan diminta memilih license sesuai kebutuhan. Dalam page ini saya akan menggunakan CC atau Creative Common.

Setelah semuanya dilengkapi kita perlu mengklik *Create Repository*.

## Pengaturan Local Environment

Pada pengaturan Local kita perlu menginstall beberapa aplikasi dasar:
- Install GitLab Client
- Install Ruby
- Install Jekyll
- Install Text Editor

Untuk panduan lengkap dalam menginstall aplikasi dasar ini, silahkan buka [Cara Membuat Local Environment Untuk GitLab Page](#){:target="_blank"}

## Clone Repositori