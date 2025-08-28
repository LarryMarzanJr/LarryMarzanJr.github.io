# Instalasi WinBox 4 Linux Native (Debian/Ubuntu)


# Instalasi WinBox 4 di Linux Native (Debian/Ubuntu)

## 1. Download Winbox 4 for Linux
Download dari situs resmi MikroTik:
```bash
wget https://download.mikrotik.com/routeros/winbox/4.0beta30/WinBox_Linux.zip
```
## 2. Extract File dan Buat Executable
```bash
unzip WinBox_Linux.zip -d WinBox_Linux
cd WinBox_Linux
chmod +x WinBox
```

## 3. Install pre-requisite paket
```bash
sudo apt update
sudo apt install -y libxcb-icccm4 libxcb-image0 libxcb-keysyms1 libxcb-render-util0 libxcb-shape0 libxcb-xfixes0 libxcb-sync1
```

## 4. Jalankan WinBox
```bash
./WinBox
```

WinBox seharusnya sudah berjalan normal tanpa error.

Semoga membantu! 

