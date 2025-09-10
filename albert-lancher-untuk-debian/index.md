# Albert Launcher Untuk Debian


## Proses Install Albert Launcher di Debian

# Debian 11
Untuk instalasi Albert Launcher di Debian 11,gunakan perintah berikut:
```bash
echo 'deb http://download.opensuse.org/repositories/home:/manuelschneid3r/Debian_11/ /' | sudo tee /etc/apt/sources.list.d/home:manuelschneid3r.list
curl -fsSL https://download.opensuse.org/repositories/home:manuelschneid3r/Debian_11/Release.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/home_manuelschneid3r.gpg > /dev/null
sudo apt update
sudo apt install albert
```

# Debian 12
Untuk instalasi Albert Launcher di Debian 11,gunakan perintah berikut:
```bash
echo 'deb http://download.opensuse.org/repositories/home:/manuelschneid3r/Debian_12/ /' | sudo tee /etc/apt/sources.list.d/home:manuelschneid3r.list
curl -fsSL https://download.opensuse.org/repositories/home:manuelschneid3r/Debian_12/Release.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/home_manuelschneid3r.gpg > /dev/null
sudo apt update
sudo apt install albert
```


# Referensi
[albert from home:manuelschneid3r project](https://software.opensuse.org/download.html?project=home:manuelschneid3r&package=albert)

