# Setup Samba Server Di Debian


## Daftar Isi  
[Proses Instalasi SMB server di Debian](#installation)

[Buat Folder untuk Sharing](#folder)

[Konfigurasi Samba](#smbconf)

[Buat Grup](#smbgroup)

[Buat User](#smbuser)

[Konfigurasi Share Folder](#shares)

[Konfigurasi Thunar File Explorer pada Debian](#thunar)

[Konfigurasi Security Policy pada Windows 10](#win10config)

[Referensi](#reference)


<a name="installation"/>

## Proses Instalasi SMB server di Debian

Install package Samba
```bash
sudo apt install samba
```

<a name="folder"/>

## Buat Folder untuk Sharing

backup smb.conf
create smb.conf from scratch
```
[global]
server string = NAS
workgroup = JR-NETWORK
security = user
map to guest = Bad User
name resolve order = bcast host
include = /etc/samba/shares.conf
```

create shares.conf
```
[music]
path = /shared/music
force user = smbuser
force group = smbgroup
create mask = 0664
force create mode = 0664
directory mask = 0775
force directory mode = 0775
public = yes
writable = yes
```
Create mask and force create mode set to 0664 is for Windows OS purposes. Because sometimes when for example people create .txt files it became executable which is wierd.


<a name="smbconf"/>

## Konfigurasi Samba

<a name="smbgroup"/>

## Buat Grup

create group
```bash
sudo groupadd --system smbgroup
```
check the group
```bash
cat /etc/group
```

<a name="smbuser"/>

## Buat User

create user
```bash
sudo useradd --system --no-create-home --group smbgroup -s /bin/false smbuser
```
check the user
```bash
cat /etc/passwd
```

<a name="shares"/>

## Konfigurasi Share Folder

change ownership of the shared folder
```
sudo chown -R smbuser:smbgroup /shared
```

add write permission to the group for the shared folder
```bash
sudo chmod -R g+w /shared
```

<a name="thunar"/>

## Konfigurasi Thunar File Explorer pada Debian

Jika Thunar File Explorer di Debian tidak bisa membuka SMB, tambahkan package sbb:
```bash
sudo apt update
sudo apt install gvfs-backends gvfs-fuse smbclient cifs-utils
```

<a name="win10config"/>

## Konfigurasi Security Policy pada Windows 10

```
Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters
```
Edit atau tambahkan binary DWORD `AllowInsecureGuestAuth` dan ubah value data menjadi `1`.

<a name="reference"/>

## Referensi
- [Learn Linux TV tentang Samba File Sharing Made Easy: Step-by-Step Linux Guide](https://www.youtube.com/watch?v=7Q0mnAT1MRg&t)
- [Novaspirit Tech YT tentang DIY NAS Server Setup with Debian / Plex / Raid 5 / Steam Library Caching / UrBackup / SMB Part 2](https://www.youtube.com/watch?v=cSi-NOlomLc&t=696s)
- [Tech Review Tech YT tentang Windows 10 You Can't Access This Shared Folder Because Your Organization's Security Policies Block Unauthenticated Guest Access.](https://www.youtube.com/watch?v=vyatMj1Z2NQ)

