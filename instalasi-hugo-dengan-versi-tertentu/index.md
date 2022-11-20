# Instalasi Hugo Dengan Versi Tertentu


### Persiapan Install Package Manager Homebrew
Sebelum instalasi Hugo di Linux, kita perlu menginstall package manager [Homebrew](https://brew.sh/). Ikuti perintah pada site tersebut untuk menginstall Homebrew. Masukkan perintah berikut:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Install Hugo Dengan Versi Tertentu
Katakanlah misalnya anda ingin menginstal Hugo dengan versi `0.62.0` maka perintah yang diketik adalah sebagai berikut:
```bash
brew extract --version=0.62.0 hugo homebrew/cask
```
Kemudian lanjutkan install dengan versi Hugo yang anda inginkan
```bash
brew install hugo@0.62.0
```
### Referensi
[Github tentang Install specific version of Hugo via Homebrew #2941](https://github.com/Homebrew/discussions/discussions/2941#discussioncomment-3205121)

<!--more-->

