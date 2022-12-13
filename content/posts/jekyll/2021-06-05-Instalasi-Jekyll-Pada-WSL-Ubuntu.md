---
title: "Instalasi Jekyll di WSL Ubuntu"
subtitle: ""
date: 2021-06-05T12:47:00+08:00
lastmod: 2021-06-05T12:47:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [jekyll]
categories: [static-site-generator]

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

https://www.vgemba.net/blog/Setup-Jekyll-WSL/


### [Software Versions](#Software Versions)

This post was written assuming the following software requirements:

Windows Environment:

Windows 10 1909
Windows Subsystem for Linux v1
Ubuntu 18.04 LTS hosted on the Microsoft Store
Jekyll:

Jekyll version 3.8.5
WSL SetupPermalink
This is well documented on the Microsoft Docs page but for completeness I will outline the steps.

First we need to install the WSL feature. Open a PowerShell prompt as an Administrator and run:
```powershell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```
Once complete press Y to reboot the computer. Once logged back in it is time to install Ubuntu from the Microsoft Store. Open a PowerShell prompt as an Administrator again:
```powershell
# Move to C:\Temp
Set-Location -Path C:\Temp

# Download Ubuntu 18.04
Invoke-WebRequest -Uri https://aka.ms/wsl-ubuntu-1804 -OutFile Ubuntu1804.appx -UseBasicParsing

# Install Ubuntu 18.04
Add-AppxPackage .\Ubuntu1804.appx
``` 
Ubuntu should now be installed on your computer and appear in the Start Menu. Start the distro and we will have to do some initial setup. You need to add a username and password on the install. This can be different from your Windows credentials.
```bash
Installing, this may take a few minutes...
Please create a default UNIX user account. The username does not need to match your Windows username.
For more information visit: https://aka.ms/wslusers
Enter new UNIX username: joenmarz
Enter new UNIX password:
Retype new UNIX password:
passwd: password updated successfully
Installation successful!
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

joenmarz@joenmarz-studio:~$
```
The next step is to update the installation with the latest patches/packages:
```bash
joenmarz@joenmarz-studio:~$ sudo apt update && sudo apt upgrade -y
```
The output above has been truncated. We now have Ubuntu 18.04 LTS installed on Windows 10.

Jekyll InstallationPermalink
Next is to install Jekyll. It is a case of broadly following the Jekyll installation guide but with one point that needs changed.

First is to install the dependencies:
```bash
sudo apt install -y ruby-full build-essential zlib1g-dev
```
Once these are installed the next step is to setup environment variables to your ~/.bashrc file:
```bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
Next up is to install Bundler:
```bash
gem install bundler
```
Finally we can install Jekyll. Now in the official install guide reference above the command given will install Jekyll v4.0.0. This is incompatible with GitHub pages as referenced in the GitHub Pages dependencies and versions. We require Jekyll v3.8.5.

It is simple to specify we want this version:
```bash
gem install jekyll --version 3.8.5
```
To check the right version of Jekyll is installed:
```bash
joenmarz@joenmarz-studio:~$ jekyll --version
jekyll 3.8.5
```
We can also list all installed Gems and compare to the GitHub Pages requried versions by running the command gem list:
```bash
joenmarz@joenmarz-studio:/mnt/c/Users/joenmarz$ gem list

*** LOCAL GEMS ***

addressable (2.7.0)
afm (0.2.2)
Ascii85 (1.0.3)
benchmark (default: 0.1.0)
bigdecimal (default: 2.0.0)
blankslate (3.1.3)
bundler (2.2.19, 2.1.4, default: 2.1.2)
cgi (default: 0.1.0)
classifier-reborn (2.2.0)
coderay (1.1.2)
colorator (1.1.0)
concurrent-ruby (1.1.8, 1.1.6)
concurrent-ruby-edge (0.6.0)
csv (default: 3.1.2)
date (default: 3.0.0)
dbm (default: 1.1.0)
delegate (default: 0.1.0)
did_you_mean (default: 1.4.0)
em-websocket (0.5.2, 0.5.1)
etc (default: 1.1.0)
eventmachine (1.2.7, 1.0.7)
fast-stemmer (1.0.2)
fcntl (default: 1.0.0)
ffi (1.15.1, 1.12.2)
fiddle (default: 1.0.0)
fileutils (default: 1.4.1)
forwardable (default: 1.3.1)
forwardable-extended (2.6.0)
gdbm (default: 2.1.0)
getoptlong (default: 0.1.0)
hashery (2.1.2)
http_parser.rb (0.6.0)
i18n (1.8.2, 0.9.5)
io-console (default: 0.5.3)
ipaddr (default: 1.2.2)
irb (default: 1.2.1)
jekyll (3.8.7, 3.8.5)
jekyll-feed (0.15.1)
jekyll-sass-converter (1.5.2)
jekyll-seo-tag (2.7.1)
jekyll-watch (2.2.1)
json (default: 2.3.0)
kramdown (1.17.0)
launchy (2.3.0)
liquid (4.0.3)
listen (3.5.1, 3.1.5)
logger (default: 1.4.2)
matrix (default: 0.2.0)
mercenary (0.3.6)
mime-types (3.3.1)
mime-types-data (3.2015.1120)
minima (2.5.1)
minitest (5.13.0)
molinillo (0.6.4)
multi_json (1.14.1)
mutex_m (default: 0.1.0)
net-http-persistent (2.9.4)
net-pop (default: 0.1.0)
net-smtp (default: 0.1.0)
net-telnet (0.1.1)
observer (default: 0.1.0)
oj (3.10.1)
open3 (default: 0.1.0)
openssl (default: 2.1.2)
ostruct (default: 0.2.0)
parslet (1.8.2)
pathutil (0.16.2, 0.16.1)
pdf-core (0.8.1)
pdf-reader (2.1.0)
posix-spawn (0.3.13)
power_assert (1.1.7)
prawn (2.2.0)
prawn-table (0.2.2)
prime (default: 0.1.1)
pstore (default: 0.1.0)
psych (default: 3.1.0)
public_suffix (4.0.6, 3.0.3)
pygments.rb (1.2.0)
racc (default: 1.4.16)
rake (13.0.1)
rb-fsevent (0.11.0)
rb-inotify (0.10.1, 0.9.10)
rdiscount (2.1.8)
rdoc (default: 6.2.1)
readline (default: 0.0.2)
readline-ext (default: 0.1.0)
redcarpet (3.5.0)
reline (default: 0.1.2)
rexml (default: 3.2.3)
rouge (3.26.0, 3.15.0)
rss (default: 0.2.8)
ruby-rc4 (0.1.5)
safe_yaml (1.0.5)
sass (3.7.4)
sdbm (default: 1.0.0)
singleton (default: 0.1.0)
stringex (2.8.4)
stringio (default: 0.1.0)
strscan (default: 1.0.3)
test-unit (3.3.5)
thor (0.19.4)
timeout (default: 0.1.0)
toml (0.2.0)
tracer (default: 0.1.0)
ttfunk (1.5.1)
uri (default: 0.10.0)
webrick (default: 1.6.0)
xmlrpc (0.3.0)
yajl-ruby (1.3.1)
yaml (default: 0.1.0)
zlib (default: 1.1.0)
```
We should now have Jekyll and its dependencies installed to publish a blog on GitHub pages.

Wrap UpPermalink
This is a simple set of steps to follow but as someone that does not know Linux very well let alone Ruby it took me a while to figure out why Jekyll was not building my site. The step of using gem install jekyll --version 3.8.5 is key to success.  
