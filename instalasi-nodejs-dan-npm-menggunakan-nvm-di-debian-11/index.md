# Instalasi Node.js dan npm Versi tertentu Menggunakan NVM (Node Version Manager) di Debian 11


## Download NVM script dari github
Kunjungi repo resmi [NVM di
Github](https://github.com/nvm-sh/nvm?tab=readme-ov-file#installing-and-updating) dan
download menggunakan curl atau wget.

Menggunakan Curl:
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

Menggunakan Wget:
```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

## List Versi Node.js
List seluruh versi Node.js dengan menjalankan perintah `nvm list-remote`.
```bash
$ nvm list-remote 
        v16.14.2   (Latest LTS: Gallium)
        v17.0.0
        v17.0.1
        v17.1.0
        v17.2.0
        v17.3.0
        v17.3.1
        v17.4.0
        v17.5.0
        v17.6.0
        v17.7.0
        v17.7.1
        v17.7.2
        v17.8.0
        v17.9.0
        v18.0.0
```
## Install Node.js versi 18 (atau versi lainnya)

Untuk menginstall node.js versi 18, ketikkan `nvm install v18
```bash
$ nvm install v18
Downloading and installing node v18.0.0...
Downloading https://nodejs.org/dist/v18.0.0/node-v18.0.0-linux-x64.tar.xz...
######################################################################### 100.0%
Computing checksum with sha256sum
Checksums matched!
Now using node v18.0.0 (npm v8.6.0)
Creating default alias: default -> v18 (-> v18.0.0)
```

Untuk install Node.js versi terbaru lewat NVM:
```bash
nvm install node
```

## Verifikasi Versi Node.js yang Terinstall
Ketikkan perintah `node -v` untuk verifikasi versi node.js yang terinstall
```bash
$ node -v
v18.0.0
```

Untuk me-list versi node.js yang terinstall di system anda, gunakan perintah `nvm ls`
```bash
$ nvm ls
->     v18.19.1
         system
default -> v18 (-> v18.19.1)
iojs -> N/A (default)
unstable -> N/A (default)
node -> stable (-> v18.19.1) (default)
stable -> 18.19 (-> v18.19.1) (default)
lts/* -> lts/iron (-> N/A)
lts/argon -> v4.9.1 (-> N/A)
lts/boron -> v6.17.1 (-> N/A)
lts/carbon -> v8.17.0 (-> N/A)
lts/dubnium -> v10.24.1 (-> N/A)
lts/erbium -> v12.22.12 (-> N/A)
lts/fermium -> v14.21.3 (-> N/A)
lts/gallium -> v16.20.2 (-> N/A)
lts/hydrogen -> v18.19.1
lts/iron -> v20.11.1 (-> N/A)
```


## Referensi
[Techviewleo.com tentang how to install node js on debian linux](https://techviewleo.com/how-to-install-node-js-on-debian-linux/)


