# Menyimpan PAT Menggunakan Git Credentials


# Apa itu Git Credentials?
Git credentials berfungsi untuk menyimpan data user dan email bahkan PAT (Personal Access
Token) kedalam cache secara lokal dalam PC kita. Hal ini sangat berfungsi pada saat
kita melakukan aktivitas mengedit repository (git add, git push, dsb.) agar kita tidak
menginput username maupun PAT secara berulang.

# Cara Menambahkan Git Credentials
Kita perlu membuat file yang akan digunakan sebagai sarana penyimpanan cache, misalnya
`~/.my-credentials`. Untuk mengaktifkan git credentials jalankan perintah berikut:
```bash
git config --global credential.helper 'store --file ~/.my-credentials'
```

Ada banyak cara untuk menyimpan cache credentials git anda. Salah satunya yaitu menggunakan
cara diatas. Untuk cara lainnya bisa anda dapatkan melalui situs resmi
[git-scm.com](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage).

# Referensi
[git-scm.com - Git Tools Credential Storage](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage)

