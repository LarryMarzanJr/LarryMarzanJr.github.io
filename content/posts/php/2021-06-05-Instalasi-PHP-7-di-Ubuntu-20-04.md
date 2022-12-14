---
title:  "Instalasi PHP 7 di Ubuntu 20.04"
subtitle: ""
date: 2021-06-05T07:20:00+08:00
lastmod: 2021-06-05T07:20:00+08:00
draft: true 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [php, ubuntu]
categories: [php]

featuredImage: ""
featuredImagePreview: ""

hiddenFromHomePage: false
hiddenFromSearch: false
twemoji: false
lightgallery: true
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

toc:
  enable: true
  auto: true
code:
  copy: true
  maxShownLines: 50
math:
  enable: false
  # ...
mapbox:
  # ...
share:
  enable: true
  # ...
comment:
  enable: true
  # ...
library:
  css:
    # someCSS = "some.css"
    # located in "assets/"
    # Or
    # someCSS = "https://cdn.example.com/some.css"
  js:
    # someJS = "some.js"
    # located in "assets/"
    # Or
    # someJS = "https://cdn.example.com/some.js"
seo:
  images: []
  # ...

---

## Cara install PHP di Ubuntu 20.04
https://tecadmin.net/install-php-ubuntu-20-04/


Read: How to Install PHP 7 on Debian via PPA
You can install multiple PHP versions on Ubuntu system and then switch PHP version as per your requirements. You can also configure Apache to run PHP web applciation’s with different-2 PHP versions.

### Langkah 1 – Add PHP PPA
First of all, you need to configure repository on your system. Run the following command to add ondrej PHP repository to your Ubuntu system.
```bash
sudo apt install software-properties-common
sudo add-apt-repository ppa:ondrej/php
```
The above command will also update the packages information list. But if you already have repository added, then update the packages information before installing or updating package:
```bash
sudo apt update
```
Once the update complete, lets begin the PHP installation.

### Langkah 2 – Install Required PHP Version
You can install any required php version on your Ubuntu system. Use one of the following options to install PHP.

Install PHP 7.4
PHP 7.4 is the latest stable version available for installation. To install PHP 7.4 on your Ubuntu system run command:
```bash
sudo apt install -y php7.4
```
Install PHP 7.3
PHP 7.3 is an current active release of PHP. The PHP team is still providing updates on this version. To install PHP 7.3 on Ubuntu, type:
```bash
sudo apt install -y php7.3
```
Install PHP 7.2
For the PHP 7.2, the development is only providing security updates and fixed. Further development on this version is stopped. To install this version run commands:
```bash
sudo apt install -y php7.2
```
Info: This repository also contains PHP 7.1 and PHP 7.0 versions. You can install them by changing the php version number in above commands.
Install PHP 5.6
PHP 5.6 is an outdated version. Its development is stopped and no more security updates available. But if you application still relies on this version use below command to install it.
```bash
sudo apt install -y php5.6
```
But it is recommended to upgrade your applications and make them compatible with latest PHP versions.

### Langkah 3 – Check PHP Version
To view the current active PHP version run the following command:
```bash
php -v

PHP 7.4.8 (cli) (built: Jul 13 2020 16:46:22) ( NTS )
Copyright (c) The PHP Group
Zend Engine v3.4.0, Copyright (c) Zend Technologies
    with Zend OPcache v7.4.8, Copyright (c), by Zend Technologies
```
### Langkah 4 – Install PHP Modules
You may also need to install modules based on your application requirements. Use the following command to search available PHP 7 modules in the package repository.
```bash
sudo apt-cache search php7*
```
You can install the required PHP modules on your system. Just change the PHP version with the packages names as per your requirements:
```bash
sudo apt install php7.4-mysql php7.4-curl php7.4-json php7.4-cgi php7.4-xsl
```
### Langkah 5 – Switch Between PHP Versions
You can use update-alternatives command to set the default PHP version. Use this tutorial to read more details about switching PHP version for CLI and Apache.
```bash
sudo update-alternatives --config php
```
Select PHP version number as per your requirement. This will change the PHP CLI version only.

There are 4 choices for the alternative php (providing /usr/bin/php).
```
  Selection    Path             Priority   Status
------------------------------------------------------------
* 0            /usr/bin/php7.4   74        auto mode
  1            /usr/bin/php5.6   56        manual mode
  2            /usr/bin/php7.2   72        manual mode
  3            /usr/bin/php7.3   73        manual mode
  4            /usr/bin/php7.4   74        manual mode

Press  to keep the current choice[*], or type selection number: 4
```
### Kesimpulan
This tutorial helps you to install PHP 7.4, 7.3, 7.2 or PHP 5.6 on your Ubuntu 20.04 system.
