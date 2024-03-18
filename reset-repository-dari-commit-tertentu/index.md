# Reset Repository Menggunakan Commit Tertentu


## Clone Repository
Lakukan Clone Repository seperti biasa
```bash
git clone <nama-repository>
```

## Melihat Commit lewat Git Log
Untuk menentukan commit yang akan kita gunakan, kita perlu mengidentifikasi Sha ID dari commit
yang akan kita gunakan dari project. Lakukan perintah
```bash
git log --oneline
```

## Checkout dari Commit Tertentu
Setelah mengetahui Sha-ID untuk commit yang rencananya akan kita gunakan, lakukan checkout
```bash
git checkout <Sha-ID>
```

## Bersihkan File Local yang tidak digunakan (Untracked Files)
Setelah checkout dari commit tertentu, biasanya terdapat file atau folder yang seharusnya
tidak ada di commit yang kita checkout, atau biasa disebut `untracked files`. Munculnya file ini karena kita melakukan clone
repository dari commit terbaru. Untuk mengetahui Untracked files tersebut, lakukan perintah
```bash
git clean -n -d
```
Untuk menghapus untracked files, lakukan perintah `git clean` dengan menambahkan flag `-f`
untuk menghapus file dan flag `-d` untuk menghapus folder/direktori.
```bash
git clean -fd
```

## Reset Repository
> **PERHATIAN** Dalam menjalankan reset repository dengan `git reset --hard`, perlu diketahui bahwa perubahan yang
> dilakukan setelah commit yang kita checkout atau _commit tebaru_ **AKAN IKUT TERHAPUS DI
> REPOSITORY YANG TELAH KITA UPLOAD**. Untuk itu pastikan melakukan **backup terhadap file
> local sebelum menjalankan perintah reset**.

Untuk melakukan reset HEAD dari repository, lakukan perintah
```bash
git reset --hard <Sha-ID>
```

## Referensi
[Opensource.com tentang git reset revert rebase commands](https://opensource.com/article/18/6/git-reset-revert-rebase-commands)

[Devopscube.com tentang checkout clone specific git commit id sha](https://devopscube.com/checkout-clone-specific-git-commit-id-sha/)

[Stackoverflow tentang How to remove untracked files from current
git](https://stackoverflow.com/questions/61212/how-do-i-remove-local-untracked-files-from-the-current-git-working-tree)

[Stackoverflow tentang How do I delete a commit from a branch](https://stackoverflow.com/questions/1338728/how-do-i-delete-a-commit-from-a-branch)

