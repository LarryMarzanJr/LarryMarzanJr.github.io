---
title: "Symlink Sebagai 'Shortcut' Untuk File Dan Folder"
subtitle: ""
date: 2022-11-21T11:34:04+08:00
lastmod: 2022-11-21T11:34:04+08:00
draft: true
author: ""
authorLink: ""
description: ""
license: ""
images: []

tags: []
categories: []

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
How to Create a Symlink for a File – Example Command
ln -s /home/james/transactions.txt trans.txt
After running this command, you will be able to access the /home/james/transactions.txt with
trans.txt. Any modification to trans.txt will also be reflected in the original file.

Note that this command above would create the link file trans.txt in your current directory.
You can as well create a linked file in a folder link this:

ln -s /home/james/transactions.txt my-stuffs/trans.txt
There must be a directory already called "my-stuffs" in your current directory – if not the
command will throw an error.

How to Create a Symlink for a Folder – Example Command
Similar to above, we'd use:

ln -s /home/james james
This would create a symlinked folder called 'james' which would contain the contents of
/home/james. Any changes to this linked folder will also affect the original folder.

How to remove a symlink
Before you'd want to remove a symlink, you may want to confirm that a file or folder is a
symlink, so that you do not tamper with your files.

One way to do this is:

ls -l <path-to-assumed-symlink>
Running this command on your terminal will display the properties of the file. In the
result, if the first character is a small letter L ('l'), it means the file/folder is a
symlink.

You'd also see an arrow (->) at the end indicating the file/folder the simlink is pointing
to.

There are two methods to remove a symlink:

How to Use Unlink to Remove a Symlink
The syntax is:

unlink <path-to-symlink>
This deletes the symlink if the process is successful.

Even if the symlink is in the form of a folder, do not append '/', because Linux will assume
it's a directory and unlink can't delete directories.

How to use rm to Remove a Symlink
As we've seen, a symlink is just another file or folder pointing to an original file or
folder. To remove that relationship, you can remove the linked file.

Hence, the syntax is:

rm <path-to-symlink>
For example:

rm trans.txt
rm james
Note that trying to do rm james/ would result an error, because Linux will assume 'james/'
is a directory, which would require other options like r and f. But that's not what we want.
A symlink may be a folder, but we are only concerned with the name.

The main benefit of rm over unlink is that you can remove multiple symlinks at once, like
you can with files.

How to Find and Delete Broken Links
Broken links occur when the file or folder that a symlink points to changes path or is
deleted.

For example, if 'transactions.txt' moves from /home/james to /home/james/personal, the
'trans.txt' link becomes broken. Every attempt to access to the file will result in a 'No
such file or directory' error. This is because the link has no contents of its own.

When you discover broken links, you can easily delete the file. An easy way to find broken
symlinks is:

find /home/james -xtype l
This will list all broken symlinks in the james directory – from files to directories to
sub-directories.

Passing the -delete option will delete them like so:

find /home/james -xtype l -delete
Wrapping up
Symbolic link are an interesting feature of Linux and UNIX systems.

You can create easily accessible symlinks to refer to a file or folder that would otherwise
not be convenient to access. With some practice, you will understand how these work on an
intuitive level, and they will make you much more efficient at managing file systems.
