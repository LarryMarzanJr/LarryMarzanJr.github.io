---
title: "Mempercepat Windows Tanpa Tools"
subtitle: ""
date: 2022-04-22T18:06:00+08:00
lastmod: 2022-04-22T18:06:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [windows]
categories: [windows]

featuredImage: ""
featuredImagePreview: ""

hiddenFromHomePage: false
hiddenFromSearch: false
twemoji: false
lightgallery: true
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

toc:
  enable: true
  auto: true
code:
  copy: true
  maxShownLines: 50
math:
  enable: false
  # ...
mapbox:
  # ...
share:
  enable: true
  # ...
comment:
  enable: true
  # ...
library:
  css:
    # someCSS = "some.css"
    # located in "assets/"
    # Or
    # someCSS = "https://cdn.example.com/some.css"
  js:
    # someJS = "some.js"
    # located in "assets/"
    # Or
    # someJS = "https://cdn.example.com/some.js"
seo:
  images: []
  # ...
---


## Atur startup
Tekan `Win+R` kemudian ketikkan
```
shell:startup
```
Lalu hapus startup yang tidak digunakan.
Tekan `Win+R` kemudian ketikkan
```
shell:common startup
```

### Atur Regedit
Tekan `Win+R` kemudian ketikkan `regedit`
```
Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\CurrentUser\run
```
Lalu disable beberapa aplikasi yang tidak digunakan

### Disable Aplikasi Startup dari Task Manager
Buka Task Manager, lalu ke Tab Startup. Disable semua aplikasi startup yang tidak anda gunakan.

### Task Scheduler
Pada menu start, buka `Task Scheduler`. Pada Task Schedule Library, disable aplikasi yang tidak digunakan seperti 
```
Edge Broser:
MicrosoftEdgeUpdateTaskMachineCore1d6dc4a73673cea
MicrosoftEdgeUpdateTaskMachineUA

MSI Afterburner:
MSIAfterburner

Node Launcher:
NvNodeLauncher_{B2FE1952-0186-46C3-BAEC-A80AA35AC5B8}

Nvidia Update:
NvDriverUpdateCheckDaily_{B2FE1952-0186-46C3-BAEC-A80AA35AC5B8}
NVIDIA GeForce Experience SelfUpdate_{B2FE1952-0186-46C3-BAEC-A80AA35AC5B8}
NvProfileUpdaterOnLogon_{B2FE1952-0186-46C3-BAEC-A80AA35AC5B8}
NvProfileUpdaterDaily_{B2FE1952-0186-46C3-BAEC-A80AA35AC5B8}

Windows Crash Report:
NvTmRep_CrashReport1_{B2FE1952-0186-46C3-BAEC-A80AA35AC5B8}
NvTmRep_CrashReport2_{B2FE1952-0186-46C3-BAEC-A80AA35AC5B8}
NvTmRep_CrashReport3_{B2FE1952-0186-46C3-BAEC-A80AA35AC5B8}
NvTmRep_CrashReport4_{B2FE1952-0186-46C3-BAEC-A80AA35AC5B8}

OneDrive:
OneDrive Per-Machine Standalone Update Task
OneDrive Reporting Task-S-1-5-21-3517565269-2653820519-3493328534-1002
``` 
Alasan mengapa tidak di delete karena setiap kali windows melakukan update, maka aplikasi yang terhapus hanya akan diinstall dan enable kembali secara otomatis oleh windows.

### Membersihkan aplikasi yang tidak terpakai
Tekan `Win+R` kemudian ketikkan
```
appwiz.cpl
```
Uninstall aplikasi yang tidak digunakan.

Masih pada appwiz.cpl yang kita buka, beralih ke tab `Turn Windows features on or off` kemudian hilangkan centang pada fitur yang tidak anda gunakan.

### Uninstall aplikasi yang tidak diperlukan dari Microsoft Store
Jalankan Microsoft Store, kemudian pada tab Library uninstall aplikasi yang tidak diperlukan.

### Debloat windows dari powershell

Buka powershell dengan hak admin dan ketikkan:
```
iex ((New-Object System.Net.WebClient).DownloadString('https://git.io/JJ8R4'))
```
Akan muncul aplikasi `Windows Toolbox by ChrisTitus` kemudian klik pada `Essential Tweaks` dan `Security Updates only`.

Setelah itu restart Windows anda. Akan terlihat perbedaan kecepatan setelah itu.

## Referensi
- [ChrisTitus - Youtube - Making Windows Faster without Tools](https://www.youtube.com/watch?v=GOz_foQcPcY)
- [ChrisTitus - Debloat Windows 10](https://christitus.com/debloat-windows-10-2020/)
