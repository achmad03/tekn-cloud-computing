# ====== <h1>
>Nama   : Achmad Syarif Abdullah                
>NIM    : 175610099
### ======= <h3>

#### Fork<h4>

* Fork adalah membuat clone dari suatu repo di GitHub milik upstream author, diletakkan ke milik kontributor. Fork hanya dilakukan sekali saja. Pada dasarnya, proses untuk fork ini meliputi:

* Fork repo di web GitHub.
* Clone fork tersebut di komputer lokal.
Kontributor harus mem-fork repo upstream author sehingga di repo kontributor muncul repo tersebut. Proses forking ini dijelaskan dengan langkah-langkah berikut:

* Login ke GitHub
* Akses repo yang akan di-fork: https://github.com/oldstager/playground
* Pada sisi kanan atas, klik Fork:

* Pilih akan ditempatkan di account mana.

* Setelah proses, repo dari upstream author sudah berada di account GitHub kita (kontributor)

Setelah itu, konfigurasikan repo lokal kontributor. Pada kondisi saat ini, di komputer lokal sudah terdapat repo playground-1 yang berada pada direktori dengan nama yang sama. Untuk keperluan berkontribusi, ada 2 nama repo yang harus diatur:

* origin: menunjuk ke repo milik kontributor di GitHub, hasil dari fork.
* upstream: menunjuk ke repo milik upstream author (repo asli) di account oldstager.
Repo origin sudah dituliskan konfigurasinya pada saat melakukan proses clone dari repo kontributor. Konfigurasi repo upstream harus dibuat.

* Tambahkan remote upstream:

* Hasil: