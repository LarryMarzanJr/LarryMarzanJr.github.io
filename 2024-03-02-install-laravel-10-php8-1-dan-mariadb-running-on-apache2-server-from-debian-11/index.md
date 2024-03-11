# Instalasi Laravel 10, PHP 8.1 dan MariaDB pada webserver Apache2 di Debian 11


# Requirements for Laravel 10, php8.1 and MariaDB running on Apache2 Server from Debian 11:

## Install Apache2 Server:
```bash
sudo apt update
sudo apt install apache2
```

## Install & configure php8.1:
```bash
sudo apt install -y lsb-release ca-certificates curl php8.1-cli php8.1-common php8.1-mysql php8.1-zip php8.1-gd php8.1-mbstring php8.1-curl php8.1-xml php8.1-bcmath
```
enable PHP extensions
```bash
sudo nvim /etc/php/8.1/apache2/php.ini
```
Uncomment the following options to enable PHP extensions fileinfo, openssl, and mbstring.
```
extension=fileinfo
extension=mbstring
extension=openssl
```

## Install & Configure MariaDB database server
Install MariaDB:
```bash
sudo apt install mariadb-server
```
After installation, login to MariaDb
```bash
sudo mysql -u root -p
```
Start to create user for database and then the database for our app
```sql
CREATE DATABASE laravelapp;
CREATE USER laravel@localhost IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON laravelapp.* TO laravel@localhost;
FLUSH PRIVILEGES;
```

## Install composer 2.3.5:
```bash
curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version=2.3.5
composer self-update 2.3.5
```


## Install & Configure Laravel 10:
Make directory for your project:
```bash
mkdir -p /var/www/{.cache,.config,projects/{html}}
```
Change ownership of the projects folder:
```bash
sudo chown -R www-data:www-data /var/www/{.cache,.config,projects}
```
Change permission of `projects` folder to 775 (rwxrwxr-x), so that the user included in group www-data can access the folder:
```bash
sudo chmod -R 775 /var/www/{.cache,.config,projects}
```

Your local debian user must be registered to `www-data` group in order to access and solve permission issue when runnig laravel app
```bash
sudo usermod -a -G www-data your_username
```

Move to you projects directory:
```bash
cd /var/www/projects/html
```

Then you can start creating new Laravel 10 app using composer:
```bash
composer create-project laravel/laravel=10.x testing-app --prefer-dist
```

After the process, your new laravel app should be created in `/var/www/projects/html/testing-app` folder.


## Configure Virtual Host for Apache2
Create a new file for apache2 module:
```bash
sudo nano /etc/apache2/sites-available/projects.conf
```
Add the following configuration inside `projects.conf` file
```html
 <VirtualHost *:80>
    ServerAdmin admin@projects                                                     
    ServerName projects                                                            
    DocumentRoot /var/www/projects/html/                                           
  
    <Directory />
        Options FollowSymLinks
        AllowOverride None
    </Directory>
    <Directory /var/www/projects/html>
        AllowOverride All
    </Directory>
 
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
 </VirtualHost>
```

Activate the Apache2 module rewrite and activate the virtual host configuration `projects.conf` using the following command.
```bash
sudo a2enmod rewrite
sudo a2ensite projects.conf
```

verify the Apache2 configuration and make sure there is no error.
```bash
sudo apachectl configtest
```

Restart the Apache2 service to apply a new virtual host configuration for the Laravel project using the below command.
```bash
sudo systemctl restart apache2
```
Now you have completed the Apache virtual host configuration for Laravel.

On your machine, edit the /etc/hosts file using nano/vim editor.
```bash
sudo nano /etc/hosts
```

Add the following configuration. be sure to change the `domain name` and `IP address` with your detailed server.
```
192.168.10.15 projects
```

Save the hosts file, and access your newly created Laravel app from `http://projects/testing-app/public`


## Refference

[StackOverflow tentang "How To Install Specified Version of Composer](https://stackoverflow.com/questions/51324721/how-to-install-specified-version-of-composer)

[DigitalOcean tentang "How To Install PHP 8.1 and set up a local development environment on ubuntu 22.04](https://www.digitalocean.com/community/tutorials/how-to-install-php-8-1-and-set-up-a-local-development-environment-on-ubuntu-22-04)

[Howtoforge tentang "Install Laravel on Ubuntu For Apache"](https://www.howtoforge.com/tutorial/install-laravel-on-ubuntu-for-apache/#prerequisites)

[Tutsmake tentang memperbaiki error "laravel log could not be opened"](https://www.tutsmake.com/how-to-fix-error-laravel-log-could-not-be-opened/)

[Laravel.com tentang minimum requirements Laravel 10](https://laravel.com/docs/10.x/releases)

