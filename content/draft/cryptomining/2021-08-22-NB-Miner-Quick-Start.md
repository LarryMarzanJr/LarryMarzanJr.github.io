---
categories: cryptomining
date: "2021-08-22T17:45:00Z"
title: NB Miner Quick Start
---

## NB Miner Quick Start

# Download NBMiner
Download NBMiner dari https://nbminer.com/

# Checksum Aplikasi NBMiner menggunakan sha256
Setelah download, pastikan aplikasi NBMiner benar-benar asli dengan memeriksa sertifikat `sha256`. Periksa file hasil download dengan mengetikkan:
```
certUtil -hashfile <nama_file> sha256
```
Contoh:
```
certUtil -hashfile NBMiner_39.0_Win.zip sha256

SHA256 hash of NBMiner_39.0_Win.zip:                                                                                    
cc600d85389374097087a208f411e65c38a85ba9bfa13745b3cff2e7d0d4d905                                                        
CertUtil: -hashfile command completed successfully.  
```
Download file sha256 file, buka file tersebut dengan text editor dan bandingkan nilai hashfile dengan yang muncul dari hasil checksum, jika nilainya sama maka file hasil download adalah asli.

Tujuan mengecek file ini adalah untuk menghindarkan kita dari serangan hacker yang memberikan link download aplikasi NBMiner palsu.

# Jalankan aplikasi Mining Anda

Cara menjalankannya tinggal mengedit batch file `*.bat` sesuai dengan coin yang ingin anda mining. Contohnya ada di sini: https://nbminer.com/#sample-usages

Sumber:

[youtube.com - How To Mine Crypto On Android [Full Guide 2021]]https://www.youtube.com/watch?v=4mwA8_q4On0){:target="_blank"} 

