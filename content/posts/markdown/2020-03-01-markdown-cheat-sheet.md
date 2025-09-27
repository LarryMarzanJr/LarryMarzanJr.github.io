---
title:  "Markdown Cheatsheet"
subtitle: ""
date:  2020-04-01T10:40:14+08:00
lastmod:  2020-04-01T10:40:14+08:00
draft: false 
author: "Larry Marzan Jr."
authorLink: ""
description: ""
license: ""
images: []

tags: [markdown]
categories: [markdown]

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

Ini adalah referensi singkat dalam menggunakan markdown.

## Headers

```no-highlight
# H1
## H2
### H3
#### H4
##### H5
###### H6

Secara alternatif, untuk H1 dan H2 dapat diganti dengan "underline" (- untuk H1 dan = untuk H2):

Alt-H1
======

Alt-H2
------
```

# H1
## H2
### H3
#### H4
##### H5
###### H6

Secara alternatif, untuk H1 dan H2 dapat diganti dengan "underline" (- untuk H1 dan = untuk H2):

Alt-H1
======

Alt-H2
------


## Emphasis

```no-highlight
Emphasis, atau italics, dengan *tanda-bintang* atau _garis-bawah_.

Strong emphasis, atau bold, dengan **tanda-bintang** atau __garis-bawah__.

Kombinasi Bold dengan **tanda-bintang dan _garis-bawah_**.

Strikethrough menggunakan dua tanda tilde. ~~Scratch this.~~
```

Emphasis, atau italics, dengan *tanda-bintang* atau _garis-bawah_.

Strong emphasis, atau bold, dengan **tanda-bintang** atau __garis-bawah__.

Kombinasi Bold dengan **tanda-bintang dan _garis-bawah_**.

Strikethrough menggunakan dua tanda tilde. ~~Scratch this.~~


## Lists

(Dalam contoh ini, tanda inden spasi ditunjukkan dengan titik-titik: ⋅)

```no-highlight
1. Item pertama
2. Item berikutnya
⋅⋅* Sub-list tanpa angka. 
1. Actual numbers don't matter, just that it's a number
⋅⋅1. Sub-list dengan angka
4. Dan Item berikutnya lagi.

⋅⋅⋅Anda bisa mendapatkan paragraf dengan inden di dalam list item. Perhatikan baris kosong diatas, dan inden (setidaknya satu, tapi kita akan menggunakan juga tiga disini untuk meluruskan Markdown).

⋅⋅⋅Untuk memperoleh baris kosong tanpa paragraf, anda akan membutuhkan dua spasi.⋅⋅
⋅⋅⋅Perhatikan garis ini terpisah, namun dalam satu paragraf.⋅⋅
⋅⋅⋅(Ini juga berlaku untuk GFM line-break)

* List tanpa urutan angka dapat menggunakan tanda bintang
- atau tanda kurang
+ Atau tanda tambah
```

1. Item pertama
2. Item berikutnya
  * Sub-list tanpa angka. 
1. Actual numbers don't matter, just that it's a number
  1. Sub-list dengan angka
4. Dan Item berikutnya lagi.

   Anda bisa mendapatkan paragraf dengan inden di dalam list item. Perhatikan baris kosong diatas, dan inden (setidaknya satu, tapi kita akan menggunakan juga tiga disini untuk meluruskan Markdown).

   Untuk memperoleh baris kosong tanpa paragraf, anda akan membutuhkan dua spasi.  
   Perhatikan garis ini terpisah, namun dalam satu paragraf.  
   (Ini juga berlaku untuk [GFM line-break](https://github.github.com/gfm/#what-is-github-flavored-markdown- "GitHub Flavored Markdown"))

* List tanpa urutan angka dapat menggunakan tanda bintang
- atau tanda kurang
+ Atau tanda tambah

## Links

Ada dua cara untuk membuat link:

```no-highlight
[Inline-style link](https://www.google.com)

[Inline-style link dengan title](https://www.google.com "Website Google")

[Reference-style link][Arbitrary case-insensitive reference text]

[Link referensi ke file repository](../blob/master/LICENSE)

[Membuka Link di Tab baru](url){:target="_blank"}

[anda dapat menggunakan referensi dengan link yang didefinisikan][1]

Atau dikosongkan saja [link dengan text ini].

URL dan URL dalam tanda kurung siku akan menjadi link secara otomatis. 
http://www.contoh.com or <http://www.contoh.com> dan kadang juga dengan contoh.com (tetapi tidak di Github, contohnya).

[arbitrary case-insensitive reference text]: https://www.mozilla.org
[1]: http://slashdot.org
[link text itself]: https://duckduckgo.com/
```

[Inline-style link](https://www.google.com)

[Inline-style link dengan title](https://www.google.com "Website Google")

[Reference-style link][Arbitrary case-insensitive reference text]

[Link referensi ke file repository](../blob/master/LICENSE)

[anda dapat menggunakan referensi dengan link yang didefinisikan][1]

Atau dikosongkan saja [link dengan text ini].

URL dan URL dalam tanda kurung siku akan menjadi link secara otomatis. 
http://www.contoh.com or <http://www.contoh.com> dan kadang juga dengan contoh.com (tetapi tidak di Github, contohnya).

[arbitrary case-insensitive reference text]: https://www.mozilla.org
[1]: http://slashdot.org
[link dengan text ini]: https://duckduckgo.com/

## Gambar

```no-highlight
Ini adalah logo saya (arahkan mouse untuk melihat title text):

Inline-style: 
![alt text](https://assets.gitlab-static.net/uploads/-/system/project/avatar/21091714/Profile_Picture3.png "Logo Title Text 1")

Reference-style: 
![alt text][logo]

[logo]: https://assets.gitlab-static.net/uploads/-/system/project/avatar/21091714/Profile_Picture3.png "Logo Title Text 2"
```

Ini adalah logo saya (arahkan mouse untuk melihat title text):

Inline-style: 
![alt text](https://assets.gitlab-static.net/uploads/-/system/project/avatar/21091714/Profile_Picture3.png "Logo Title Text 1")

Reference-style: 
![alt text][logo]

[logo]: https://assets.gitlab-static.net/uploads/-/system/project/avatar/21091714/Profile_Picture3.png "Logo Title Text 2"

## Koding dan Syntax Highlighting

Code block adalah bagian dari keistimewaan dari Markdown, tapi tidak pada highlight syntax. Namun beberapa renderer seperti Gitlab dan Github mensupport syntax highlighting. Bagaimana perlakuan highlight pada kode program bergantung pada masing-masing renderer. Untuk melihat daftar selengkapnya, dan cara menuliskan nama pemrograman, lihat pada [laman demo highlight.js](http://softwaremaniacs.org/media/soft/highlight/test.html).

```no-highlight
Inline `code` ditandai dengan `tanda petik`
```

Inline `code` ditandai dengan `tanda petik`

Kode yang panjang dapat ditandai dengan tiga tanda petik <code>```</code> di awal dan akhir dari baris kode, atau dengan menambahkan empat spasi / inden. Saya sarankan dengan menggunakan tiga tanda petik saja di awal dan akhir barisan kode, karena lebih mudah dan bisa support syntax highlighting.
 
<pre lang="no-highlight"><code>```javascript
var s = "Syntax highlighting untuk Javascript";
alert(s);
```
 
```python
s = "Syntax highlighting untuk Python"
print s
```
 
```
Pada blok ini tidak ditandai dengan bahasa pemrograman apapun.
sehingga tidak ada syntax highlighting, tulisannya hanya polos.
Walaupun diinput kode html, contohnya &lt;b&gt;tag&lt;/b&gt;.
```
</code></pre>

```javascript
var s = "Syntax highlighting untuk Javascript";
alert(s);
```

```python
s = "Syntax highlighting untuk Python"
print s
```

```
Pada blok ini tidak ditandai dengan bahasa pemrograman apapun.
sehingga tidak ada syntax highlighting, tulisannya hanya polos.
Walaupun diinput kode html, contohnya <b>tag</b>.
```

## Tabel

Tabel bukan bagian inti dari Markdown, tapi pembuatan tabel juga di support. Ini adalah bagian mudah dalam menambahkan tabel di email anda, daripada harus copy-paste tabel dari aplikasi lain.

```no-highlight
Tanda titik-dua dapat digunakan untuk mensejajarkan kolom

| Tabel    | Mudah                | Digunakan   |
| -------- |:--------------------:| -----------:|
| kolom 3  | disejajarkan kekanan | Rp 1000.000 |
| kolom 2  | di tengah            | Rp 500.000  |
| kolom 1  | disejajarkan kekiri  | Rp 20.000   |

Harus ada setidaknya 3 garis yang memisahkan setiap header pada tabel.
There must be at least 3 dashes separating each header cell.
Garis vertikal (|) pada bagian luar tabel tidak harus diketik, dan
anda tidak perlu membuat tabel sejajar pada saat pengetikan karena akan otomatis diatur pada saat sudah ditampilkan pada laman anda.

Markdown | Tidak | Sejajar
--- | --- | ---
*Namun* | `tabelnya` | **tetap rapih**
1 | 2 | 3
```

Tanda titik-dua dapat digunakan untuk mensejajarkan kolom

| Tabel    | Mudah                | Digunakan   |
| -------- |:--------------------:| -----------:|
| kolom 3  | disejajarkan kekanan | Rp 1000.000 |
| kolom 2  | di tengah            | Rp 500.000  |
| kolom 1  | disejajarkan kekiri  | Rp 20.000   |

Harus ada setidaknya 3 garis yang memisahkan setiap header pada tabel.
There must be at least 3 dashes separating each header cell.
Garis vertikal (|) pada bagian luar tabel tidak harus diketik, dan
anda tidak perlu membuat tabel sejajar pada saat pengetikan karena akan otomatis diatur pada saat sudah ditampilkan pada laman anda.

Markdown | Tidak | Sejajar
--- | --- | ---
*Namun* | `tabelnya` | **tetap rapih**
1 | 2 | 3

## Blockquotes

```no-highlight
> Blockquotes sangat berguna dalam me-reply email.
> Baris ini adalah bagian dari quote yang sama

Quote terputus.

> Ini adalah contoh baris yang sangat panjang tapi tetap masuk dalam quote ketika berpindah baris. Mari kita coba membuat baris ini lebih panjang dengan menambahkan kalimat. Di dalam quote anda juga dapat menambahkan **Markdown** dan pasti berfungsi.
```

> Blockquotes sangat berguna dalam me-reply email.
> Baris ini adalah bagian dari quote yang sama

Quote terputus.

> Ini adalah contoh baris yang sangat panjang tapi tetap masuk dalam quote ketika berpindah baris. Mari kita coba membuat baris ini lebih panjang dengan menambahkan kalimat. Di dalam quote anda juga dapat menambahkan **Markdown** dan pasti berfungsi.

## Inline HTML

You can also use raw HTML in your Markdown, and it'll mostly work pretty well. 

```no-highlight
<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>
```

<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>

## Horizontal Rule
```
Three or more...

---

Hyphens

***

Asterisks

___

Underscores
```

Three or more...

---

Hyphens

***

Asterisks

___

Underscores

<a name="lines"/>

## Line Breaks

My basic recommendation for learning how line breaks work is to experiment and discover -- hit &lt;Enter&gt; once (i.e., insert one newline), then hit it twice (i.e., insert two newlines), see what happens. You'll soon learn to get what you want. "Markdown Toggle" is your friend. 

Here are some things to try out:

```
Here's a line for us to start with.

This line is separated from the one above by two newlines, so it will be a *separate paragraph*.

This line is also a separate paragraph, but...
This line is only separated by a single newline, so it's a separate line in the *same paragraph*.
```

Here's a line for us to start with.

This line is separated from the one above by two newlines, so it will be a *separate paragraph*.

This line is also begins a separate paragraph, but...  
This line is only separated by a single newline, so it's a separate line in the *same paragraph*.

(Technical note: *Markdown Here* uses GFM line breaks, so there's no need to use MD's two-space line breaks.)

## YouTube Videos

They can't be added directly but you can add an image with a link to the video like this:

```no-highlight
<a href="http://www.youtube.com/watch?feature=player_embedded&v=YOUTUBE_VIDEO_ID_HERE
" target="_blank"><img src="http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>
```

Or, in pure Markdown, but losing the image sizing and border:

```no-highlight
[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg)](http://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)
```

Referencing a bug by #bugID in your git commit links it to the slip. For example #1. 
