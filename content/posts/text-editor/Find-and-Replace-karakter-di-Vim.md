---
title: "Find and Replace Karakter Di Vim"
subtitle: ""
date: 2022-11-12T14:36:41+08:00
lastmod: 2022-11-12T14:36:41+08:00
draft: true
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [vim]
categories: [text-editor]

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
  disqus:
    enable: true
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

<!--more-->
Artikel ini menggambarkan cara melakukan find and replace text di vim.

Secara umum perintah yang digunakan sebagai berikut:
```
:[range]s/{pattern}/{string}/[flags] [count]
```

The command searches each line in [range] for a {pattern}, and replaces it with a {string}.
[count] is a positive integer that multiplies the command.
If no [range] and [count] are given, only the pattern found in the current line is replaced.  The current line is the line where the cursor is placed.
For example, to search for the first occurrence of the string ‘foo’ in the current line and
replace it with ‘bar’, you would use:

:s/foo/bar/
Copy
To replace all occurrences of the search pattern in the current line, add the g flag:

:s/foo/bar/g
Copy
If you want to search and replace the pattern in the entire file, use the percentage
character % as a range. This character indicates a range from the first to the last line of
the file:

:%s/foo/bar/g
Copy
If the {string} part is omitted, it is considered as an empty string, and the matched
pattern is deleted. The following command deletes all instances of the string ‘foo’ in the
current line:

:s/foo//g
Copy
Instead of the slash character (/), you can use any other non-alphanumeric single-byte
character except as a delimiter. This option is useful when you have the ‘/’ character in
the search pattern or the replacement string.
:s|foo|bar|
Copy
To confirm each substitution, use the c flag:
:s/foo/bar/gc
Copy
replace with bar (y/n/a/q/l/^E/^Y)?
Copy
Press y to replace the match or l to replace the match and quit. Press n to skip the match
and q or Esc to quit substitution. The a option substitutes the match and all remaining
occurrences of the match. To scroll the screen down, use CTRL+Y, and to scroll up, use
CTRL+E.

