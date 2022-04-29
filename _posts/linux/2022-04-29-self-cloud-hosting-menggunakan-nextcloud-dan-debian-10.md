---
layout: post
title:  "Self Cloud Hosting Menggunakan Nextcloud dan Debian 10"
date:   2022-04-29 08:02:00 +0800
category: linux
---

INSTALL REQUIRED PACKAGES:
```bash
sudo apt install apache2 libapache2-mod-php7.3 mariadb-server php7.3-xml php7.3-cli php7.3-cgi php7.3-mysql php7.3-mbstring php7.3-gd php7.3-curl php7.3-zip
```

ENABLE PHP 7.3
```bash
sudo a2enmod php7.3
```

RESTART APACHE2 SERVICE:
```bash
sudo systemctl restart apache2
```

CONFIGURE MARIADB:
```bash
sudo mysql_secure_installation
```

```bash
NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none):
OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MariaDB
root user without the proper authorisation.

You already have a root password set, so you can safely answer 'n'.

Change the root password? [Y/n] n
 ... skipping.

By default, a MariaDB installation has an anonymous user, allowing anyone
to log into MariaDB without having to have a user account created for
them.  This is intended only for testing, and to make the installation
go a bit smoother.  You should remove them before moving into a
production environment.

Remove anonymous users? [Y/n] y
 ... Success!

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] y
 ... Success!

By default, MariaDB comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] y
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] y
```

DATABASE SETUP:
```bash
sudo mysql -u root -p
```
setup:
```sql
CREATE DATABASE nextcloud;
CREATE USER 'joenmarz'@'localhost' IDENTIFIED BY 'C@k4l4ng**';
GRANT ALL ON nextcloud.* TO 'joenmarz'@'localhost';
FLUSH PRIVILEGES;
\q
```

NEXTCLOUD INSTALLATION
Download Nextcloud 17:
```bash
wget https://download.nextcloud.com/server/releases/nextcloud-17.0.0.zip
```

Unzip Nextcloud 17:
```bash
unzip nextcloud-17.0.0.zip
```

Copy nextcloud folder to webserver:
```bash
sudo cp -rv nextcloud /var/www/html/nextcloud
```

Gain access to nextcloud folder recursively:
```bash
sudo chown -R www-data:www-data /var/www/html/nextcloud
```

## Referensi
[EF - Linux Made Simple - How to install Nextcloud on Debian 10](https://www.youtube.com/watch?v=P_SXZ_K3-e4){:target="_blank"}
