# Autostart Tmux Saat Akses Lewat SSH


## Kegunaan
Ketika kita menjalankan login lewat `SSH`, kita bisa menggunakan session manager dengan
membuka aplikasi `Tmux`. Namun jika Tmux sering anda gunakan maka anda dapat menjalankannya
secara otomatis saat login SSH.

## Edit Konfigurasi Shell
Untuk menjalankan Tmux secara otomatis saat login SSH, maka tambahkan perintah pada shell
profile anda. Jika menggunakan `bash` maka dapat diedit dari file `.bashrc`. Jika
menggunakan `zsh` maka dapat diedit dari file `.zshrc`. Tambahkan perintah berikut:
```bash
if [ -z "$TMUX" ]; then
    tmux attach -t default || tmux new -s default
fi
```

## Referensi
[Ostechnix - Autostart Tmux Session On Remote System When Logging In Via SSH](https://ostechnix.com/autostart-tmux-session-on-remote-system-when-logging-in-via-ssh/)

