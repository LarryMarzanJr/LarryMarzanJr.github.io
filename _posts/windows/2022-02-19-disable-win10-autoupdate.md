---
title: 'Cara disable auto update pada Windows 10'
layout: post
categories: windows
tags: windows
date: 2022-02-19 15:33:00 +0800
---

### Disable Windows Update pada menu Services
Klik `Start` kemudian ketikkan `services`. Double klik pada `Windows Update` kemudian ubah startup type menjadi `disabled` dan apply settingan anda.

### Disable Windows Update pada menu Registry
Tekan tombol `Win + R`, ketikkan `regedit` dan tekan `Enter`. Dari menu Regedit kita buka menu tree berikut:
```
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\wuauserv
```
##### ImagePath
Double klik pada `ImagePath` kemudian pada value data
```
%systemroot%\system32\svchost.exe -k netsvcs -p
```
ubah `svchost.exe` menjadi `svchost0.exe` sehingga value data menjadi:
```
%systemroot%\system32\svchost0.exe -k netsvcs -p
```
##### DependOnService
Double klik pada `DependOnService` kemudian pada value data `rpcss` diganti menjadi `rpcss0`.

Sampai disini auto update Windows 10 telah berhasil dinonaktifkan.

## Referensi
- [Youtube - How to Disable the Latest Windows 10 Update 2020](https://www.youtube.com/watch?v=0qQMpsfj2hw&t=284s){:target="_blank"}