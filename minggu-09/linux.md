# ======= <h1>
> Nama: Achmad Syarif Abdullah
> NIM: 175610099
### ======= <h3>

### Mengkloning GitHub Laboratorium, Repo <h3>
Gunakan perintah berikut untuk mengkloning repo lab dari GitHub (Anda dapat mengklik perintah atau mengetiknya secara manual). Ini akan membuat salinan repo laboratorium di sub-direktori baru bernama linux_tweet_app.   
    ![GitHub Logo](/minggu-09/Gambar/1.PNG)

### Jalankan satu tugas dalam wadah Alpine Linux <h3>
Pada langkah ini kami akan memulai sebuah wadah baru dan memintanya untuk menjalankan perintah nama host. Kontainer akan mulai, jalankan perintah hostname, lalu keluar.

Jalankan perintah berikut di konsol Linux Anda.   
    ![GitHub Logo](/minggu-09/Gambar/2.PNG)

Docker menjaga wadah berjalan selama proses itu dimulai di dalam wadah masih berjalan. Dalam hal ini proses nama host keluar segera setelah output ditulis. Ini artinya wadah berhenti. Namun, Docker tidak menghapus sumber daya secara default, sehingga wadah masih ada dalam status Keluar.

### Daftar semua wadah. <h3>
Jalankan wadah Ubuntu interaktif
Anda dapat menjalankan sebuah wadah berdasarkan versi Linux yang berbeda dari yang dijalankan pada host Docker Anda.
    ![GitHub Logo](/minggu-09/Gambar/3.PNG)
Pada contoh berikut, kita akan menjalankan wadah Ubuntu Linux di atas host Alpine Linux Docker (Play With Docker menggunakan Alpine Linux untuk node-node-nya).
    ![GitHub Logo](/minggu-09/Gambar/4.PNG)

### Jalankan wadah Docker dan akses cangkangnya.

Jalankan perintah berikut dalam wadah.
    ![GitHub Logo](/minggu-09/Gambar/5.PNG)
ls / akan mencantumkan isi dari root director di dalam container, ps aux akan menunjukkan proses yang sedang berjalan di dalam container, cat / etc / issue akan menunjukkan distro Linux mana yang dijalankan container, dalam hal ini Ubuntu 18.04.3 LTS.   
    ![GitHub Logo](/minggu-09/Gambar/6.PNG)

Untuk bersenang-senang, mari kita periksa versi VM host kami.   
    ![GitHub Logo](/minggu-09/Gambar/7.PNG)

Jalankan latar belakang wadah MySQL
Wadah latar belakang adalah cara Anda menjalankan sebagian besar aplikasi. Ini contoh sederhana menggunakan MySQL.

### Jalankan wadah MySQL baru dengan perintah berikut.

Daftar wadah yang sedang berjalan.   
    ![GitHub Logo](/minggu-09/Gambar/8.PNG)
Anda dapat memeriksa apa yang terjadi di wadah Anda dengan menggunakan beberapa perintah Docker bawaan: log kontainer buruh pelabuhan dan bagian atas wadah buruh pelabuhan.
    ![GitHub Logo](/minggu-09/Gambar/9.PNG)
Mari kita lihat proses yang berjalan di dalam wadah.   
    ![GitHub Logo](/minggu-09/Gambar/10.PNG)

Anda juga dapat menggunakan exec container docker untuk terhubung ke proses shell baru di dalam wadah yang sudah berjalan. Menjalankan perintah di bawah ini akan memberi Anda shell interaktif (sh) di dalam wadah MySQL Anda.   
    ![GitHub Logo](/minggu-09/Gambar/11.PNG)

Mari kita periksa nomor versi dengan menjalankan perintah yang sama lagi, hanya kali ini dari dalam sesi shell baru di wadah.   
    ![GitHub Logo](/minggu-09/Gambar/12.PNG)