# Menyimpan Session Tmux


# Menyimpan Session Tmux

## Membuat Session Tmux Menggunakan Nama

Kita perlu menamakan session agar memudahkan ketika session tersebut akan dipanggil kembali.
Gunakan perintah berikut:
```bash
tmux new -s 'my session'
```
Setelah itu kita akan session tersebut akan otomatis terbuka. Perlu diketahui bahwa session
ini masih bersifat sementara, artinya ketika kita exit dari terminal maka session ini akan
hilang. Untuk itu kita perlu menginstall plugin tmux yang dapat menyimpan session
`my session` tersebut. Lakukan dettach session dengan menekan `Ctrl + b` kemudian `d`.
Setelah itu lanjut dengan instalasi plugin.

## Plugin Manager

Untuk menyimpan session kita perlu menambahkan plugin di Tmux. Namun untuk menambahkan
plugin, kita perlu menginstall plugin manager. Download plugin dengan mengetikkan:
```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

Kemudian buat file konfigurasi `.tmux.conf` pada home folder
```bash
nvim ~/.tmux.conf
```
dan tambahkan konfigurasi di dalamnya:
```
# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
 
# Other examples:
# set -g @plugin 'github_username/plugin_name'
# set -g @plugin 'git@github.com/user/plugin'
# set -g @plugin 'git@bitbucket.com/user/plugin'
 
# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run -b '~/.tmux/plugins/tpm/tpm'
```

## Plugin Untuk Menyimpan Session
Setelah plugin manager diinstall, tambahkan plugin
[Tmux-Resurrect](https://github.com/tmux-plugins/tmux-resurrect) pada file `.tmux.conf`
```
set -g @plugin 'tmux-plugins/tmux-resurrect'
```
Setelah itu kita perlu menginstall plugin yang sudah ditambahkan tadi. Masuk ke session
tmux `my session` yang telah kita bentuk dari awal
```bash
tmux attach-session -t 'my session'
```
Setelah masuk di session tersebut tekan `Ctrl + b` kemudian `Ctrl + I` (huruf "i" kapital) agar
plugin akan diinstal. Dan jika sudah berhasil install maka akan muncul pesan
```bash
TMUX environment reloaded.
Done, press ESCAPE to continue.
```

## Menyimpan dan Memanggil Session
Untuk menyimpan session kita hanya perlu menekan `Ctrl + b` kemudian `Ctrl + s`

Kita bisa membuat sebanyak mungkin session dan menyimpannya. Untuk memanggil session yang
kita inginkan tekan `Ctrl + b` kemudian `s`, maka list session yang sudah disimpan akan
muncul dan dapat dibuka kembali.
## Referensi

[MakeTechEasier tentang How to Manage and Restore Tmux Sessions in Linux](https://www.maketecheasier.com/manage-restore-tmux-sessions-linux/)

[StackExchange tentang How to save multiple sessions in tmux](https://superuser.com/questions/1010075/how-to-save-multiple-sessions-in-tmux/1287933#1287933)

