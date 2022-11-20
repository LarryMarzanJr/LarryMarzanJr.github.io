# Perkenalan GitLab Pages


## GitLab Pages

Adalah Page yang gratis, hosted, static yang bisa anda taruh di GitLab.
- Bisa sebagai Web Page yang memperkenalkan produk-produk anda
- Bisa berfungsi sebagai Blog
- Bisa sebagai Website Lengkap, semua tergantung anda

Dan ini benar-benar gratis yah..
Ketika [membuat Akun GitLab](https://gitlab.com/users/sign_up){:target="_blank"} anda dapat membuat Repo dan Web Page yang tidak terbatas jumlahnya.

Ada beberapa situasi dimana anda perlu menggunakan GitLab Pages dan saya akan memperjelasnya kepada anda sekarang.

# Sebagai Web Page (html atau markdown)
Yang paling lazim adalah ketika anda memiliki aplikasi, dan anda membuat kodenya dan memberitahukan kepada orang-orang bahwa anda memiliki aplikasi. Lalu mereka melihatnya dan bertanya, dokumentasinya mana? Jadi anda bisa menggunakan GitLab Pages untuk membuat dokumentasi dari aplikasi anda.
Dalam Laman Web Page dengan beberapa links, seperti Logo di bagian atas, dan beberapa tulisan text dan screenshot.
Jadi disini anda hanya membuat Laman HTML atau Markdown.

# Sebagai Blog
Alasan lain bagi anda menggunakan GitLab Pages, karena anda ingin membuat Blog! Dengan blog itu anda ingin orang-orang melihatnya dan biasanya mereka kemudian membagikan konten anda.
Anda membuat ini sebagai cara untuk membuat "branding" anda sendiri, atau untuk Aplikasi/Program anda, atau menggunakannya untuk membagi hal-hal yang telah anda pelajari.

# Sebagai Website Lengkap
Alasan mendasar yang ketiga kenapa anda menggunakan GitLab Pages adalah membuat Website yang lengkap dengan sub-laman seperti Deskripsi (About Us), Produk, Dokumentasi, dan juga Blog anda sendiri.
Bahkan tidak perlu harus menampilkan laman GitLab. Anda dapat menampilkan hanya tentang Website anda saja untuk produk anda, tanpa orang-orang harus mengakses akun GitLab. Tentunya hal ini dapat anda bangun seiring waktu dalam membuat laman anda.

## Pembuatan GitLab Pages
Ada dua metode dalam pembuatan GitLab Pages.
Pertama anda mendesign page anda dengan membuat Static Page, Laman Resume, atau Dokumentasi dari produk anda. Biasanya didalamnya hanya ada text, gambar dan style website yang temanya bisa anda download.

Yang kedua dengan menggunakan [Jekyll](https://jekyllrb.com "Website Jekyll"){:target="_blank"}, yang merupakan sebuah framework yang didesign khusus untuk membuat static page khusus untuk GitLab Pages tanpa menggunakan database. Jadi ketika anda membuat sebuah Dokumentasi page lewat Jekyll, GitLab secara otomatis mendeteksi file dan menambahkannya ke Website sehingga orang-orang bisa langsung membacanya.

## Contoh Repositori GitLab Pages
Mari kita lihat contoh Repository GitLab Page yang saya buat dan saya namakan repo-contoh. Kemudian saya menambahkan file README.md yang isi tulisannya "Selamat datang di Repo saya".
Saya masuk ke setingan Repositori GitLab yang saya buat ini (repo-contoh), kemudian meminta GitLab untuk membuat root folder (/) sebagai GitLab Pages. Sehingga ketika seseorang membuka URL lain yang saya bentuk sebagai alamat Web Page, maka mereka hanya akan melihat tampilan README.md sebagai sebuah Laman.
Hal ini dimungkinkan dengan adanya CDN atau Content Distribution Network pada GitLab. Jadi selain bisa dilihat dalam tampilan Web Page, file konten yang anda buat juga dapat dilihat dari GitLab Repository sebagai sebuah File Markdown. Orang-orang pun dapat berkontribusi pada konten atau Repositori yang anda buat.
Jekyll dalam hal ini memberikan kemudahan dengan menempatkan semua file markdown yang anda buat ke dalam satu folder dan secara otomatis menampilkannya pada web page anda. Jadi anda tinggal menulis artikel ataupun dokumentasi ke dalam sebuah file markdown.

## Fasilitas Pengeditan (Development Environment)
Ini adalah bagian dimana anda menggunakan fasilitas editor untuk menulis Dokumentasi atau artikel anda.

# Environment Web
Alternatif pertama, yaitu beberapa orang memanfaatkan Website [GitLab](https://GitLab.com){:target="_blank"} yang memiliki fitur editor lewat browser, dan langsung mengetik Dokumentasi dari GitLab.

# Environment Lokal
Atau anda dapat melakukan cloning repositori anda secara lokal atau didownload ke komputer anda, mengedit dokumentasi secara offline menggunakan Text Editor kemudian ketika selesai lalu anda mensinkronkannya kembali (upload) repository GitLab. Dalam hal ini anda menginstall:
- `Text Editor` yang bisa mensupport syntax highlighting seperti *[Visual Studio Code](https://code.visualstudio.com "VSCode Website"){:target="_blank"}*, *Sublime Text*, *Notepad++*, *Atom* dan masih banyak lagi text editor lainnya yang dapat anda pilih sesuai selera.
- `GitLab Client` yaitu [git](https://git-scm.com/downloads "Git Website"){:target="_blank"} yang berfungsi untuk melakukan clone(download) repositori, sinkronisasi(upload) hasil editan anda. Atau secara umum bisa mengedit repositori anda secara remote.
- `Jekyll` adalah [Framework](https://jekyllrb.com "Jekyll Framework"){:target="_blank"}  untuk mensuport website GitLab Page anda.
- `Ruby` [Programming Language](https://www.ruby-lang.org/en/ "Ruby Website"){:target="_blank"}. Karena Framework Jekyll dibangun menggunakan Ruby sehingga program ini juga wajib diinstall.

## Konfigurasi Saya
Dalam konfigurasi ini saya menggunakan *[ArchLinux](https://www.archlinux.org "ArchLinux Website"){:target="_blank"}* sebagai Distribusi Sistem Operasi sehingga proses instalasinya menjadi sangat mudah. Jika anda ingin menggunakan Arch Linux saya bisa mengajari cara menginstallnya.

Bagi anda yang mungkin menggunakan Sistem Operasi lainnya seperti *Microsoft Windows* dan *Apple MacOS* tentunya bisa juga menggunakannya, namun yang pasti cara menginstallnya menjadi sedikit berbeda. Mungkin kedepannya saya akan membuat artikel tentang cara melakukan setup Local Environment GitLab Pages lewat kedua jenis Sistem Operasi Ini.

Selanjutnya saya akan bahas tentang: [Membangun GitLab Page Secara Mendasar](# "Tutor 2 - Membangun GitLab Page Secara Mendasar"){:target="_blank"}
