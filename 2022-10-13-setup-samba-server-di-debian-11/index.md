# Setup Samba Server Di Debian 11


## Daftar Isi  
[Proses Instalasi SMB server di Debian](#installation)

[Konfigurasi Security Policy pada Windows 10](#win10config)

[Referensi](#reference)


<a name="installation"/>

## Proses Instalasi SMB server di Debian

Install package Samba
```bash
sudo apt install samba
```

Konfigurasi sharing folder pada samba service dilakukan di `/etc/samba/smb.conf`.
```bash
sudo nano /etc/samba/smb.conf
```
Kemudian pada bagian bawah file tambahkan argumen berikut:
```
# additional share for my Hardisk
[datastore]
 path = /srv/pool/datastore
 force group = nogroup
 create mask = 0755
 directory mask = 0755
 browsable = yes
 writeable = yes
 guest ok = yes
```

Struktur folder harus kita ubah sehingga semua user termasuk guest dapat mengakses folder sharing ini:
```bash
sudo chown nobody:nogroup /srv/pool/datastore
```

<a name="win10config"/>

## Konfigurasi Security Policy pada Windows 10

```
Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters
```
Edit atau tambahkan binary DWORD `AllowInsecureGuestAuth` dan ubah value data menjadi `1`.

<a name="reference"/>

## Referensi
- [Novaspirit Tech YT tentang DIY NAS Server Setup with Debian / Plex / Raid 5 / Steam Library Caching / UrBackup / SMB Part 2](https://www.youtube.com/watch?v=cSi-NOlomLc&t=696s){:target="_blank"}
- [Tech Review Tech YT tentang Windows 10 You Can't Access This Shared Folder Because Your Organization's Security Policies Block Unauthenticated Guest Access.](https://www.youtube.com/watch?v=vyatMj1Z2NQ){:target="_blank"}

