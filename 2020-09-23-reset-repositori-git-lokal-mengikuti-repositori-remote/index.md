# Reset Git Repositori Lokal Mengikuti Repositori Remote


<!-- Sumber: -->
<!-- https://stackoverflow.com/questions/1628088/reset-local-repository-branch-to-be-just-like-remote-repository-head -->

# Restore Repositori
Katakanlah anda "blunder" pada mengedit repositori lokal dan ingin meresetnya sesuai Repositori yang tersimpan terakhir di Web anda. Lakukan perintah ini:
```bash
git fetch origin
git reset --hard origin/main
```
# Backup Repositori
Sebaliknya, katakanlah repositori lokal saat ini ingin anda simpan sementara, atau belum live, maka simpanlah di branch tersendiri sebagai backup. Lakukan perintah ini:
```
git commit -a -m "komentar anda"
git branch <nama_branch_baru>
git push origin <nama_branch_baru>
```

Sehingga contohnya menjadi seperti ini:
```
git commit -a -m "Simpan Pekerjaan saya, untuk jaga-jaga"
git branch simpan-kerjaan
git push origin simpan-kerjaan
```

