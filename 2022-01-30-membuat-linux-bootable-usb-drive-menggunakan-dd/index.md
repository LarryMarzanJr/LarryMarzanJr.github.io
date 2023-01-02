# Membuat Linux bootable USB drive menggunakan DD


# Membuat Linux bootable USB drive menggunakan DD

dd adalah aplikasi/perintah paling sederhana pada linux yang digunakan dalam menyalin image ISO kedalam USB Flashdisk.

Dengan menggunakan dd anda dapat membuat bootable USB Linux sistem dengan menyalin image kedalam USB drive.

Anda dapat membuat bootable USB untuk ArchLinux, Manjaro, Ubuntu, Linux Mint, dan berbagai varian linux lainnya.

Anda juga dapat mencoba pendekatan ini dalam mambuat bootable Windows USB, jika anda menyalin image ISO Windows ke dalam USB drive.

Berikut adalah langkah-langkahnya:

### Menyalin ISO ke dalam USB flash drive
Jalankan perintah:
```bash
sudo dd bs=4M if=/path/to/iso of=/dev/sdX status=progress && sync
```

Ganti /dev/sdX dengan nama device USB anda.
Untuk mengetahui mana device USB anda, dapat dicek dengan perintah:
```
sudo fdisk -l
```

### Mengembalikan / Restore USB flash drive ke kondisi semula

Bersihkan flash drive anda:
```bash
sudo wipefs --all /dev/sdX
```
> Note: `/dev/sdX` bisa berubah-ubah `/dev/sdb, ..sdc, dst.` tergantung banyaknya media
> penyimpanan yang terpasang pada komputer anda. Dalam hal ini jika media penyimpanan selain
> hardisk utama anda hanya ada 1 flashdisk, maka jika kita list menggunakan `lsblk` maka
> akan muncul pilihan partisi `/dev/sdb`.

Buat partisi baru:
```bash
sudo cfdisk /dev/sdX
```
Pada saat muncul `Select Label type` pilih dos. Buatlah sebuah partisi primary sehingga akan
terbentuk partisi. yaitu `/dev/sdb1`, Setelah itu write perubahan anda.

Format partisi menjadi FAT file system:
```bash
sudo mkfs.vfat -n 'label-USB-anda' /dev/sdX1
```

