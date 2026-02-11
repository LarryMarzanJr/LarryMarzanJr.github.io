# xfce4-terminal Emulator Favorit di XFCE Debian


# xfce4-terminal Emulator Favorit di XFCE dan Debian

## Mengapa Pakai xfce4-terminal
Karena ini terminal bawaan xfce yang interfacenya cukup mudah digunakan. Terdapat opsi GUI
yang bisa mempermudah kita kustomasi tampilan terminal emulator. Namun untuk bisa membuat
tampilan tersebut permanen kita perlu menjalankannya dengan tambahan command line misalnya
`xfce4-terminal --command-line`. List lengkap command line dapat dilihat pada
[dokumentasi resmi command line xfce4-terminal](https://docs.xfce.org/apps/xfce4-terminal/command-line).

---

## Menjalankan Terminal Emulator
Untuk menjalankan xfce4-terminal pada debian, kita perlu menginstall packagenya dulu
```bash
sudo apt install xfce4-terminal
```
Kemudian bisa kita jalankan perintah `xfce4-terminal` untuk menjalankan terminal emulator
ini. Atau bisa juga melalui GUI Desktop Environment kita bisa run program xfce-terminal.

---

## Kustomasi Tampilan Terminal

Pada saat xfce4-terminal dijalankan, saya suka membuat tampilan terminal lebih bersih dengan
menambahkan beberapa command line.
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

