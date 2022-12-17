# Cara Install Node Js Di Debian 11


# Persiapan Sebelum Install Node Js
Kita perlu mengupdate packages dan install _curl_
```bash
sudo apt update && sudo apt install -y curl
```

# Install Node Js Sesuai Pilihan Versi

- v14.x (Active LTS)
- v12.x (Maintenance LTS)
- v16.x (Latest Version)

> v14.x (LTS)
```bash
curl -fsSL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt install -y nodejs
```

> v12.x (LTS)
```bash
curl -fsSL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt install -y nodejs
```

> v16.x
```bash
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt install -y nodejs
```

# Referensi
[ItzGeek - How to Install Node Js and Npm On Debian 11](https://www.itzgeek.com/how-tos/linux/debian/how-to-install-node-js-and-npm-on-debian-11.html)

