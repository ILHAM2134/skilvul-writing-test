# Unix Command Line

### Pengenalan CLI
- CLI merupakan salah satu cara bagaimana user dapat **berinteraksi, mengakses, dan berkomunikasi** dengan OS. dengan CLI, user berkomunikasi dengan OS melalui sebuah baris kode yang akan dieksekusi oleh sistem. Setiap OS populer seperti Linux, Windows, dan MacOS memiliki CLI nya sendiri, seperti terminal dan powershell.

- Selain CLI, user juga dapat berkomunikasi dengan Operating System melalui GUI, GUI adalah cara mudah bagaimana user dapat beirnteraksi dengan OS melalui tampilan grafis yang interaktif, sehingga lebih memudahkan pengguna.
- Contoh CLI yang populer antara lain :
	- sh
	- bash
	- zsh
	- cmd.exe
- Istilah - istilah :
	- Shell : program yang digunakan untuk berkomunikasi / memerintah sistem.
	- Command Line Interface : jenis shell yang berbasis teks
	- Terminal emulator : aplikasi untuk mengakses CLI
### Navigasi menggunakan CLI
- Filesystem dalam OS mengatur bagaimana data disimpan di dalam sebuah system
- Sistem operasi Windows & Unix-like menyusun file dan direktori menggunakan struktur yang bentuknya mirip tree, contohnya sebagai berikut :

![contoh-img](https://ibb.co/wwY7KFJ)

- Command basic untuk navigasi di dalam Unix-like CLI  :
	- pwd (print working directory) : untuk melihat *current working directory* 
	- ls (lists) : melihat isi file yg ada dalam sebuah direktori
	- cd (change directory) : pindah direktori
	
- Pathname
	- absolute pathname : pathname yang mengacu kepada root directory dan bersifat universal di setiap working directory
		```
		/User/user/Work/GitHub/skilvul/tugas
		```
	- relative pathname : dimulai dari current working directory
		```
		./catatan
	
		./silvul/folder-lain
		```


### Command Manipulasi Files dan Direktori
- Command untuk melihat isi files
	- head : melihat beberapa line awal dari sebuah file text
	- tail : melihat beberapa line akhir dari sebuah fie text
	- cat : melihat isi sebuah file
- Membuat file / direktori
	- touch : membuat sebuah file
	-  mkdir : membuat sebuah direktori
- Menyalin, memindahkan, dan menghapus files / directory
	- cp (copy) : manyalin files / directory
	- mv (move) : memindahkan files / directory, bisa juga untuk rename
	- rm (remove) : menghapus file / directory

# HTML
### Pendahuluan
- HTML ( Hyper Text Markup Languange), digunakan untuk menampilkan konten pada browser, bisa berupa teks, img, video, link, dll
- Dengan adanya berbagai macam tools, akan membuat pembuatan kode menjadi lebih cepat dan efisien, salah satu tools dev populer adalah VSCode yan menyediakan berbagai tools dan ekstensi untuk memudahkan developer dalam melakukan pengembangan

### Dasar HTML
- kita bisa saja menjalankan text html langsung di browser dan tidak menimbulkan error, tetapi akan lebih baik jika penulisan html melibatkan penggunaan tag, elemen html, dll
- HTML tersusun atas hierarki elemen yang memiliki tingkatan parent-child, element parent merupakan elemen yang berada setingkat diatas current element, sedangkan element child merupakan element yang dikandung oleh current element sebanyak satu tingkat di bawah
- Anatomi elemen HTML terdiri tag pembuka, konten, dan penutup. tag pembuka dapat dipasangi atribut yang bisa melakukan banyakhal, salah satunya adalah styling dan menambah fungsionalitas
- HTML comment digunakan untuk menandai kode HTML yang hendak diabaikan oleh browser (tidak dieksekusi / tidak ditampilkan), comment yang baik harus bisa memberikan penjelasan kepada sesama programmer agar bisa memahami kode
- cara menjalankan / menampilkan file HTML adalah membukanya lewat browser, tetapi cara inimemiliki kekurangan, yaitu harus direfresh apabila hendak memuat ulang kode HTML yag telah diperbaiki
- cara ini bisa diatasi dengan menggunakan ekstensi VSCode, yaitu live serveryang bisa melakukan auto-reload apabila file disave

### Struktur HTML
```
<html>
	<head>
		<meta blablabla>
		<link rel="stylesheet" href="./file-css.css">
		<title>JUDUL</title>
	</head>
	<body>
		/* konten HTML yg ditampilkan browser
		akan diletatakan dalam element body */
	</body>
</html>
```

# CSS
### Pendahuluan
- CSS (Cascading Style Sheet) berfungsi untuk memodifikasi element HTML agar tampak lebih cantik, kita dapat menerapkan styling seperti merubah warna, font, ukuran, layouting, dll
- Struktur CSS terdiri dari selector elemen HTML, diikuti dengan *curly bracket* dan styling yang hendak diterapkan pada element tersebut

```
.selector {
	styling pada selector
}
```
- kita juga bisa memberikan coment pada CSS agar baris kode yang diberi coment tidak dieksekusi oleh browser

```
/* baris ini tidak akan dieksekusi*/

.selector {
	styling
}

/* ini juga tidak
akan dieksekusi */
```
cara menerapkan CSS pada HTML terbagi menjadi
- inline
```
<elemenHTML style="atribut: value;"> </elemenHTML>
```

- style pada head
```
<head>
	<style>
		.selector {
			atribut: value;
		}
	</style>
</head>
```
- eksternal CSS
```
<head>
	<link src="./source/code.css>
<head>
```

# Javascript
### Pendahuluan
- Merupakan bahasa pemrograman yg awalnya dikembangkan untuk mengembangkan interaktifitas dari web page, sebelum akhirnya merambah ke berbagai sektor, seperti ke back end (node) front end (react, vue, angular)
- JS juga mempunyai syntax coment yang menyebabkan kode tidak dieksekusi interpreter
	```
	// kode ini tidak dijalankan, tapi hanya satu baris yg tidak dijalankan

	/* kode
	ini
	tidak
	dijalankan */
	```
- JS memiliki berbagai tipe data, antara lain :
	- number : tipe data berupa angka, mendukung operasi aritmetik
	- string : tipe data berupa teks (huruf, angka, simbol, dll)
	- boolean : tipe data yang berisi dua nilai kebenaran (truth / false)
	- null : tipe data yang tidak memiliki nilai, tapi bukan berarti kosong
	- undefined : tipe data apabila variabel diinisialissi tanpa meng-assign nilainya kedalam variabel tersebut
	- tipe data non-primitif :
		- object : terdiri dari kumpulan key-value
		- array : terdiri dari data data jenis apapun yan disusun berurutan berdasarkan indexing
- variabel digunakan sebagai wadah utk menyimpan data dengan tipe tertentu
	- var : variabel yang fleksibel, nilainya bisa direassign dan juga bisa didefinisikan ulang
	- let : variabel yang hanya bisa direassign oleh tipe data yang sama dengan tipe data awal, tidak dapat di-redeclare
	- const : variabel yang tidak dapat di-reassign maupun di-redeclare
- operator digunakan untuk mengoperasikan data agar menghasilkan suatu **value**
	- assignment operator : memasukkan value kedalam suatu variabel
	- increment & decrement : melakukan penambahan / pengurangan nilai sebanyak 1
	- aritmethic operator : operator matematika ( kali, bagi, tambah, kurang, modulus)
	- comparison operator : operator pembanding yg megembalikan nilai boolean ( >, <, <=, >=, ==, ===, dll)
	- logical operator : operator yang mengembalikan nilai boolean ( AND(&&), OR( || ), NOT( ! ), dll)
- JS juga mempunyai conditional statement
	- truthy & falsy : suatu nilai non-boolean yang dianggap memiliki nilai true / false
	- conditional statement pada JS
		- if, mengevaluasi suatu nilai boolean, apabila true, maka kode di dalamya akan dieksekusi
		- switch, mengevaluasi suatu nilai, apabila nilainya sesuai dengan case, maka kode di dalamnyaakan dieksekusi
		- ternary, merupakan shorthand dalam pengkondisian
```
kondisi ? kode ini dijalankan apabila true : kode ini dijalankan apabila false
```

- JS juga mempunyai looping statement
	- jenis looping
		- for loop
			```
			for(nilai awal; nilai stopping; step) {
				// instruksi yang dijalankan
			}
			```
		- while loop
			```
			while(nilai yg dievaluasi) {
				// kode yang akan dijalankan
				incrment / decrement
			}
			```
		- do while
			```
			do {
				// kode yang akan dijalankan

				increment  / decrement
			} while (kondisi)
			```
	- nested loop : looping yang terjadi di dalam looping

# Algoritma
- pengertian : suatu rangkaian proses berurutan yang didefinisikan secara jelas
- pentingnya algoritma dlm pemrograman yaitu agar bisa mendefinisikan program dengan jelas dan terarah
- jenis proses algoritma
	- sequence : proses algoritma yang terjadi secara berurutan, proses selanjutnya tidak bisa dijalankan apabila proses saat ini belum selesai dijalankan
	- selection : proses pengkondisian, hanya melaksanakan program yang sesuai kriteria
	- iteration : algoritma perulangan
	- concurent : algoritma asynchronous
- cara menulis algoritma
	- deskriptif : menjabarkan algoritma dengan teks secara detail
	- flow chart : menggambarkan proses algoritma dengan diagram dengan kaidah kaidah tertentu
	- pseudo code : menjabarkan algoritma dalam bentuk yang mendekati bahasa pemrograma

# Git & GitHub Dasar
### Pendahuluan
- pengertian : suatu VCS yang populer digunakan oleh developer
- instalasi git bisa dilakukan pada OS Windows, Linux, dan Mac OS
- konfigurasi git : mangatur nilai username dan email pada git
```
# mengatur username
git config --global user.name "nama-kita"

# mengatur email
git config --global user.email "emailkita@domain.com"
```
### Tahapan bekerja dengan git
- tahapan stage pada git
	- working directory
	- staging area
	- commit

### Command pada git
- command dasar git
	- git init`: membuat repository baru
	- git status`: check repository status
	- git add`: menambahkan files ke “staging”
	- git commit`: menyimpan files di “staging” sebagai commit
	- git log`: melihat histori perubahan

- command git untuk kembali ke masa lalu
	- git diff` untuk melihat detail perubahan
	- git checkout` untuk kembali ke commit tertentu
	- git reset` untuk reset files ke sebuah commit, perubahan di branch yang dihapus menjadi ‘untracked files’
	- git revert` untuk undo commit, perubahan disimpan dalam commit
	- Files yang perubahannya diabaikan didaftarkan pada .gitignore

- command git pada branching
	- git branch` untuk melihat branch yang ada. Branch aktif ditandai dengan `*
	- git branch nama_branch` untuk membuat branch baru
	- git merge branch_target` untuk menggabungkan perubahan atau histori dari branch_target ke branch saat ini

- command git pada remote
	- Remote repository, tempat untuk menyimpan git repo di internet
	- git remote` untuk melihat daftar remote di repository
	- git remote add` untuk menambahkan remote
	- git push` untuk mengirim perubahan ke remote repository
	- git fetch` untuk mengambil metadata dari remote
	- git pull` untuk mengambil perubahan dari remote ke local
	- “Pull Request”, proses review merge yang dibuat

- command git utk kolaborasi
	- git clone` untuk menyalin remote repository ke komputer kita
	- Github fork untuk membuat copy dari repository orang lain ke akun kita
