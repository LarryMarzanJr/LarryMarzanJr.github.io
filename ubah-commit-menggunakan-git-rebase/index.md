# Ubah Commit Menggunakan Git Rebase

## Periksa Log Hasil Commit
Untuk mengetahui perubahan atau hasil commit yang dilakukan di repository anda, lakukan perintah
```bash
git log --oneline
```
Dengan demikian kita dapat mengetahui `Sha-ID` dari setiap commit yang dilakukan seperti contoh berikut.
```bash
280f1fe make migration `create settings table`
db3e02c make migration `create sale details table`
81289eb make migration `create sales table`
```
## Rebase
Misalnya kita ingin melakukan rebase mulai dari Sha-ID `db3e02c`, maka kita perlu menggunakan Sha-ID sebelum commit tersebut, yaitu pada Sha-ID `81289eb`. Maka perintah rebase menjadi seperti berikut ini
```bash
git rebase -i 81289eb
```
Rebase bisa juga dilakukan dengan cara menghitung urutan `HEAD` dari git log. Misalnya kita ingin melakukan rebase dari commit terakhir, dalam hal ini `280f1fe`, maka bisa dengan perintah berikut
```bash
git rebase -i HEAD~1
```
> `~1` pada `HEAD~1` menunjukkan pada urutan commit ke berapa kita akan melakukan rebase, sehingga untuk melakukan urutan ke2 terakhir bisa menjadi `git rebase -i HEAD~2`

## Push Force
Setelah rebase dilakukan maka hasil commit secara lokal telah berubah. Untuk mengupdate commit dari sisi remote tentunya kita perlu melakukan git push. Dalam hal ini kita wajib menambahkan flag `--force` atau `-f` untuk dapat mengupdate commit di sisi remote.
```bash
git push --force

