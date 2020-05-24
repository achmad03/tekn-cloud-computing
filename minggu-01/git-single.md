# Installasi <h1>
>Nama   : Achmad Syarif Abdullah                
>NIM    : 175610099
### Windows <h3>

* Setelah download Git, double click pada file yang di-download. Akan dimunculkan lisensi. Klik Next untuk lanjut.
    ![GitHub Logo](/minggu-01/Gambar/inst/1.JPG)
* Setelah itu, pilih lokasi instalasi. Secara default akan terisi C:\Program Files\Git. Ganti lokasi jika memang anda menginginkan lokasi lain, klik Next   
    ![GitHub Logo](/minggu-01/Gambar/inst/2.JPG)
* Pilih komponen. Tidak perlu diubah-ubah, sesuai dengan default saja. Klik pada Next.
    ![GitHub Logo](/minggu-01/Gambar/inst/3.JPG)
* Mengisi shortcut untuk menu Start. Gunakan default (Git), ganti jika ingin mengganti - misalnya Git VCS.
    ![GitHub Logo](/minggu-01/Gambar/inst/4.JPG)
* Pilih editor yang akan digunakan bersama dengan Git. Pada pilihan ini, digunakan Notepad++.

* Pada saat instalasi, Git menyediakan akses git melalui Bash maupun command prompt. Pilih pilihan kedua supaya bisa menggunakan dari dua antarmuka tersebut. Bash adalah shell di Linux. Dengan menggunakan bash di Windows, pekerjaan di command line Windows bisa dilakukan menggunakan bash - termasuk ekskusi dari Git.
    ![GitHub Logo](/minggu-01/Gambar/inst/5.JPG)
* Pilih OpenSSL untuk HTTPS. Git menggunakan https untuk akes ke repo GitHub atau repo-repo lain (GitLab, Assembla).

* Pilih pilihan pertama untuk konversi akhir baris (CR-LF).   
    ![GitHub Logo](/minggu-01/Gambar/inst/6.JPG)
* Pilih PuTTY untuk terminal yang digunakan untuk mengakses Git Bash.   
    ![GitHub Logo](/minggu-01/Gambar/inst/7.JPG)
* Untuk opsi ekstra, pilih serta aktifkan 1 dan 2.   
    ![GitHub Logo](/minggu-01/Gambar/inst/8.JPG)
* Setelah itu proses instalasi akan dilakukan.   
    ![GitHub Logo](/minggu-01/Gambar/inst/10.JPG)
* Jika selesai akan muncul dialog pemberitahuan. Klik pada Finish.   
    ![GitHub Logo](/minggu-01/Gambar/inst/11.JPG)
* Untuk menjalankan, dari Start menu, ketikkan "Git", akan muncul beberapa pilihan. Pilih "Git Bash" atau "Git GUI".   
    ![GitHub Logo](/minggu-01/Gambar/inst/new/1.jpg)
* Tampilan jika akan menggunakan "Git Bash"   
    ![GitHub Logo](/minggu-01/Gambar/inst/new/2.jpg)
* Tampilan jika akan menggunakan "Git GUI"   
    ![GitHub Logo](/minggu-01/Gambar/inst/new/3.jpg)
* Untuk mencoba dari command prompt, masuk ke command prompt, setelah itu eksekusi "git --version" untuk melihat apakah sudah terinstall atau belum. Jika sudah terinstall dengan benar, makan akan muncul hasil berikut:
    ![GitHub Logo](/minggu-01/Gambar/inst/new/4.jpg)

### Konfigurasi <h3>

Secara minimal, user harus memberitahu Git tentang username serta email yang digunakan setiap kali terjadi perubahan pada repo Git. Username serta email ini yang akan dimasukkan oleh Git ke catatan perubahan di repo. Di sistem operasi Linux atau sejanis (UNIX), konfigurasi ini nantinya akan disimpan di $HOME/.gitconfig. Untuk sistem operasi Windows, konfigurasi ini akan disimpan di C:\Document and Settings\NamaUser dengan nama file .gitconfig. Secara minimal, ada 2 hal yang perlu dikonfigurasi yaitu username dan email. Gunakan perintah berikut:   
    ![GitHub Logo](/minggu-01/Gambar/conf/4.PNG)   
Isian di atas harus disesuaikan dengan nama serta email yang digunakan untuk mendaftar di GitHub. Untuk melihat konfigurasi yang sudah ada:
    ![GitHub Logo](/minggu-01/Gambar/conf/5.jpg)

### Mengelola Repo Sendiri <h3>

#### Mengelola Repo Sendiri <h4>

##### Mengelola Repo Sendiri <h5>
* Klik tanda + pada bagian atas setelah login, pilih New repository   
    ![GitHub Logo](/minggu-01/Gambar/7.jpg)
* Isikan nama, keterangan, serta lisensi. Jika dikehendaki, bisa membuat repo Private
    ![GitHub Logo](/minggu-01/Gambar/8.jpg)
* Klik Create Repository   
Setelah langkah-langkah tersebut, repo akan dibuat dan bisa diakses menggunakan pola https://github.com/username/reponame. Pada repo tersebut, hanya akan muncul 1 file, yaitu LICENSE. Jika memilih membuat README pada saat langkah ke 2, juga akan muncul README.md. Ada atau tidak ada README.md tidak mempunyai efek apapun pada langkah ini.

##### Clone Repo <h5>
* Proses clone adalah proses untuk menduplikasikan remote repo di GitHub ke komputer lokal. Untuk melakukan proses clone, gunakan perintah berikut:
    ![GitHub Logo](/minggu-01/Gambar/10.jpg)
* Setelah perintah ini, di direktori awesome-project akan disimpan isi repo yang sama dengan di GitHub. Perbedaannya, di komputer lokal terdapat direktori .git yang digunakan secara internal oleh Git.

##### Mengelola Repo <h5>
* Setelah clone ke komputer lokal, semua manipulasi konten dilakukan di komputer lokal dan hasilnya akan di-push ke remote repo di GitHub. Dengan demikian, jangan berganti-ganti remote lokal, sekali dibuat disitu, tetap berada disitu. Jika kehilangan repo lokal, clone ulang ke direktori yang bersih (kosong) setelah itu baru lakukan pengelolaan repo. Beberapa hal yang biasanya dilakukan akan diuraikan berikut ini.

###### Mengubah Isi - Push Tanpa Branching dan Merging <h6>
Perubahan isi bisa terjadi karena satu atau kombinasi beberapa hal berikut:   

* File dihapus
* File diedit
* Membuat file / direktori baru
* Menghapus direktori  

Untuk kasus-kasus tersebut, lakukan perubahan di komputer lokal, setelah itu push ke repo.   
    ![GitHub Logo](/minggu-01/Gambar/12.jpg)
    ![GitHub Logo](/minggu-01/Gambar/13.jpg)
* Cara ini lebih mudah tetapi mempunyai resiko jika terjadi kesalahan dalam edit. Cara yang lebih aman tetapi memerlukan langkah yang lebih panjang adalah branching and merging

###### Mengubah Isi dengan Branching and Merging <h6>
Dengan menggunakan cara ini, setiap kali akan melakukan perubaham, perubahan itu dilakukan di komputer lokal dengan membuat suatu cabang yang nantinya digunakan untuk menampung perubahan-perubahan tersebut. Setelah itu, cabang itu yang akan dikirim ke repo GitHub untuk dimintai review kemudian digabungkan (merge) ke master. Secara umum, repo yang dibuat biasanya sudah mempunyai satu branch yang disebut dengan master. Cara ini lebih aman, terstruktur, terkendali, dan mempunyai history yang lebih baik. Jika perubahan yang kita buat sudah terlalu kacau dan kita menyesal, maka ada cara untuk "membersihkan" repo lokal kita. Secara umum, langkahnya adalah sebagai berikut:   

* Buat branch untuk menampung perubahan-perubahan
* Lakukan perubahan-perubahan
* Add dan commit perubahan-perubahan tersebut ke branch
* Kembali ke repo master
* Buat pull request di GitHub
* Merge pull request di GitHub
* Merge branch untuk menampung perubahan-perubahan tersebut ke master.
* Selesai.   

    ![GitHub Logo](/minggu-01/Gambar/15.jpg)

* Setelah itu, kirim pull request (PR):
    ![GitHub Logo](/minggu-01/Gambar/16.jpg)
* Setelah membuat PR, PR tersebut bisa di-merge:
    ![GitHub Logo](/minggu-01/Gambar/17.jpg)
* Setelah itu, Confirm Merge, branch yang kita kirimkan tadi sudah dimasukkan ke branch master. Setelah itu, merge di komputer lokal:
    ![GitHub Logo](/minggu-01/Gambar/18.jpg)

###### Sinkronisasi <h6>
Suatu saat, bisa saja terjadi kita menggunakan komputer lain dan mengedit repo melalui repo lokal di komputer lain, setelah itu pindah ke kamputer lain lagi. Saat itu, kita perlu melakukan sinkronisasi ke kemputer lokal. Perintah untuk sinkronisasi adalah:
    ![GitHub Logo](/minggu-01/Gambar/181.jpg)
Perintah ini dikerjakan di direktori tempat repo lokal kita berada.
###### Membatalkan Perubahan <h6>
Praktik yang baik adalah membuat branch pada saat kita akan melakukan perubahan-perubahan. Jika perubahan-perubahan yang kita lakukan sudah sedemikian kacaunya, maka kita bisa membuat supaya perubahan-perubahan yang kacau tersebut hilang dan kembali ke kondisi bersih seperti semula.
    ![GitHub Logo](/minggu-01/Gambar/20.jpg)

###### Undo Commit Terakhir <h6>
* Suatu saat, mungkin kita sudah terlanjur mem-push perubahan ke repo GitHub, setelah itu kita baru menyadari bahwa perubahan tersebut salah. Untuk itu, kita bisa melakukan git revert.

* Contoh di atas adalah contoh untuk mengubah README.md dengan beberapa commit. Setelh itu, kita akan mengembalikan ke posisi terakhir sebelum commit terakhir.

* Perintah di atas akan membuka editor. Pada editor tersebut kita bisa mengetikkan pesan revert ( = pesan commit untuk pembatalan). Setelah selesai, simpan:

* Selanjutnya, tinggal di-push ke repo GitHub.

* Jika commit sudah dilakukan, tetapi belum di-push ke repo GitHub (masih berada di lokal), cara membatalkannya:

* Untuk kembali ke perubahan pada saat yang sudah lama, yang perlu dilakukan adalah melakukan git revert <posisi> kemudian mengedit secara manual kemudian push ke repo.

* Setelah itu, jika dilihat pada file, akan muncul tambahan untuk memudahkan meng-edit. File ini harus di-resolve terlebih dahulu, setelah itu baru di add dan commit:

* Edit file tersebut, setelah itu simpan.

* Setelah itu, lanjutkan proses revert. Saat git revert --continue isikan pesan revert.