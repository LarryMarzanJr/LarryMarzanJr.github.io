# Menggunakan Tmux


## Daftar Isi  
[Apa itu Tmux?](#tmux_intro)

[Membuat Session Baru](#create_session)

[Membuka Tmux Session](#open_session)


<a name="tmux_intro"/>

## Apa itu Tmux?

Tmux adalah aplikasi yang memungkinkan kita membuat session tersendiri di dalam terminal shell. Session tersebut bisa kita biarkan berjalan walaupun terminal sudah diclose. Keuntungan memakai session tmux salah satunya ketika kita mengakses shell secara remote menggunakan ssh, kita bisa mengakses session tmux yang sedang aktif.

Untuk menginstall tmux pada distro linux anda, silahkan melihat referensi pada [repository resmi tmux](https://github.com/tmux/tmux/wiki/Installing)


<a name="create_session"/>

## Membuat Session Baru
### Session Baru
Untuk membuat session baru di Tmux jalankan
```bash
> tmux
```
### Session Baru dengan label Nama
Untuk membuat session baru yg memiliki label nama di Tmux jalankan
```bash
> tmux new -s nama_session_anda
```

<a name="open_session"/>

## Membuka Tmux Session

Untuk memperoleh daftar session yang sedang aktif dalam sebuah [shell](https://www.tutorialspoint.com/unix/unix-what-is-shell.htm), gunakan perintah `tmux ls`
```bash
> tmux ls
0: 1 windows (created Sat Feb 26 23:51:00 2022)
```
Diatas menunjukan ada satu session tmux yang sedang aktif yaitu session 0. Jika ada lebih dari satu session maka akan muncul `0: ..`, `1: ..`, `2: ..` dan seterusnya. Untuk memilih session 0 kita gunakan perintah berikut
```bash
> tmux attach-session -t 0
```
dan ini akan membuka session 0 yang sedang aktif.

## Referensi
- [medium.com tentang What is tmux and why would you want it for frontend development?](https://medium.com/@tholex/what-is-tmux-and-why-would-you-want-it-for-frontend-development-e43e8f370ef2)
- [poopcode.com tentang attach to tmux session](https://poopcode.com/attach-to-tmux-session/)

