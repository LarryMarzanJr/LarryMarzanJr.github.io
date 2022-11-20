# Cara Install Nodejs NPM di Linux Debian


# Cara Install Nodejs NPM di Linux Debian
Pada terminal, ketikkan:
```
sudo apt install nodejs npm
```

Setelah itu tambahkan tulisan ini pada file `.bashrc` anda:

npm set prefix ~/.npm
PATH="$HOME/.npm/bin:$PATH"
PATH="./node_modules/.bin:$PATH"
