# xfce4-terminal Terminal Favorite di XFCE dan mudah digunakan


# xfce4-terminal Sebagai Terminal andalan di XFCE 

## Apa itu
**SCP (Secure Copy Protocol)** adalah perintah di sistem operasi berbasis Unix/Linux yang digunakan untuk **menyalin file atau direktori antar komputer melalui jaringan** dengan aman. SCP memanfaatkan protokol **SSH (Secure Shell)** untuk melakukan otentikasi dan enkripsi data, sehingga lebih aman dibandingkan protokol lama seperti `ftp` atau `rcp`.

Dengan SCP, kita bisa:
- Menyalin file dari komputer lokal ke server remote.
- Mengambil file dari server remote ke komputer lokal.
- Menyalin file dari satu server remote ke server remote lainnya.

---

## Menjalankan Terminal Emulator
Pada xfce kita bisa run command `xfce4-terminal` untuk menjalankan terminal emulator ini.

---

## Kustomasi Tampilan Terminal

Pada saat xfce4-terminal dijalankan, saya suka membuat tampilan terminal lebih bersih dengan
menambahkan beberapa flag.
  * `--maximize` fungsinya agar saat xfce4-terminal dibuka maka tampilan window dalam
    keadaan maximize.
  * `--hide-menubar` menyembunyikan menubar (yang ada menu File, Edit, dst.)di bagian atas
    terminal emulator.
  * `--hide-scrollbar` menyembunyikan scrollbar di bagian samping kanan terminal emulator.
  * `--hide-borders` menyembunyikan border yang menampilkan tombol maximize, minimize, dan
    close.

Sehingga perintah untuk menjalankan terminal dapat dirampung menjadi
```bash
xfce4-terminal --maximize --hide-menubar --hide-scrollbar --hide-borders
```

