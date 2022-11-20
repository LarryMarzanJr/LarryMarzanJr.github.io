# Instalasi Linux lewat WSL


### Install WSL
Langkah pertama: Enable Developer Mode
The first thing you need to do is enable developer mode on your Windows machine.

Go to `Settings -> Update and Security -> For developers`,kemudian klik `Developer mode`

Selanjutnya Install WSL. Masuk ke menu Start dan cari `turn windows features on or off`. Select that, then check the “Windows Subsystem for Linux (Beta)” checkbox.

### Install Linux lewat WSL
Untuk mengetahui list disribution Linux yang tersedia secara online, buka aplikasi `Powershell` kemudian ketikkan:
```
wsl --list --online
```
![Powershell](https://www.ntweekly.com/wp-content/uploads/2021/09/image-3-1024x387.png "Powershell")
Misalnya kita memilih distro Ubuntu untuk diinstal, maka ketikkan:
```
wsl --install -d Ubuntu
```

## Referensi
- [Microsoft tentang Install WSL](https://docs.microsoft.com/en-us/windows/wsl/install){:target="_blank"}
- [wsl-guide.kennethreitz.org tentang Installing WSL](https://wsl-guide.kennethreitz.org/en/latest/installation.html){:target="_blank"}
- [ntweekly.com tentang Install WSL distribution using Command](https://www.ntweekly.com/2021/09/10/list-available-for-install-wsl-distribution-using-command/){:target="_blank"}



