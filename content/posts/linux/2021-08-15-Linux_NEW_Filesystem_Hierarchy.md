---
title: "Hirarki Filesystem Linux"
subtitle: ""
date: 2021-08-15T13:44:00+08:00
lastmod: 2021-08-15T13:44:00+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: [] 

tags: [linux]
categories: [linux]

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

## Hirarki Filesystem Linux

| Path |  Description |
| :---: |:--------------------:|
| `/` |	The top-level directory is the root filesystem and contains all of the files required to boot the operating system before other filesystems are mounted as well as the files required to boot the other filesystems. After boot, all of the other filesystems are mounted at standard mount points as subdirectories of the root. |
| `/bin` |  Contains essential command binaries. |
| `/boot` |	Consists of the static bootloader, kernel executable, and files required to boot the Linux OS. |
| `/dev` |	Contains device files to facilitate access to every hardware device attached to the system. |
| `/etc` |	Local system configuration files. Configuration files for installed applications may be saved here as well. |
| `/home` |	Each user on the system has a subdirectory here for storage. |
| `/lib` |	Shared library files that are required for system boot. |
| `/media` |	External removable media devices such as USB drives are mounted here. |
| `/mnt` |	Temporary mount point for regular filesystems. |
| `/opt` |	Optional files such as third-party tools can be saved here. |
| `/root` |	The home directory for the root user. |
| `/sbin` |	This directory contains executables used for system administration (binary system files). |
| `/tmp` |	The operating system and many programs use this directory to store temporary files. This directory is generally cleared upon system boot and  may be deleted at other times without any warning. |
| `/usr` |	Contains executables, libraries, man files, etc. |
| `/var` |	This directory contains variable data files such as log files, email in-boxes, web application related files, cron files, and more. |

Sumber:

[hackthebox.eu - Linux File System Hierarchy](https://academy.hackthebox.eu/module/18)
