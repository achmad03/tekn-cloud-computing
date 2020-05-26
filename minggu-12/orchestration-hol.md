# ======= <h1>
> Nama: Achmad Syarif Abdullah
> NIM: 175610099
### ======= <h3>

### Bagian 1: Apa itu Orkestrasi <h3>
Jadi, apa itu orkestrasi? Yah, orkestrasi mungkin paling baik digambarkan menggunakan contoh. Katakanlah Anda memiliki aplikasi yang memiliki lalu lintas tinggi bersama dengan persyaratan ketersediaan tinggi. Karena persyaratan ini, Anda biasanya ingin menggunakan setidaknya 3+ mesin, sehingga jika tuan rumah gagal, aplikasi Anda masih dapat diakses dari setidaknya dua lainnya. Jelas, ini hanya sebuah contoh dan kasus penggunaan Anda kemungkinan akan memiliki persyaratan sendiri, tetapi Anda mendapatkan idenya.

### Bagian 2: Konfigurasikan Mode Swarm <h3>
Aplikasi dunia nyata biasanya digunakan di beberapa host seperti yang dibahas sebelumnya. Ini meningkatkan kinerja aplikasi dan ketersediaan, serta memungkinkan komponen aplikasi individu untuk skala secara mandiri. Docker memiliki alat asli yang tangguh untuk membantu Anda melakukan ini.
    ![GitHub Logo](/minggu-12/Gambar/01.PNG)
    ![GitHub Logo](/minggu-12/Gambar/2.PNG)

### Langkah 2.1 - Buat simpul Manajer <h3>
Pada langkah ini Anda akan menginisialisasi Swarm baru, bergabung dengan node pekerja tunggal, dan verifikasi operasi berhasil.
    ![GitHub Logo](/minggu-12/Gambar/3.PNG)
    ![GitHub Logo](/minggu-12/Gambar/4.PNG)

### Langkah 2.2 - Gabung node Pekerja ke Swarm <h3>
Anda akan melakukan prosedur berikut pada node2 dan node3. Menjelang akhir prosedur, Anda akan beralih kembali ke node1.

Sekarang, ambil seluruh buruh pelabuhan bergabung ... perintah kami salin sebelumnya dari node1 di mana ia ditampilkan sebagai terminal output. Kita perlu menempelkan perintah yang disalin ke terminal node2 dan node3.
    ![GitHub Logo](/minggu-12/Gambar/5.PNG)

### Bagian 3: Menyebarkan aplikasi di beberapa host <h3>
Sekarang setelah Anda memiliki swarm up dan running, sekarang saatnya untuk menggunakan aplikasi tidur kami yang sangat sederhana.

Anda akan melakukan prosedur berikut dari node1.

### Langkah 3.1 - Menyebarkan komponen aplikasi sebagai layanan Docker <h3>
Aplikasi tidur kami menjadi sangat populer di internet (karena mengenai Reddit dan HN). Orang suka itu. Jadi, Anda harus mengukur aplikasi Anda untuk memenuhi permintaan puncak. Anda harus melakukan ini di beberapa host untuk ketersediaan tinggi juga. Kami akan menggunakan konsep Layanan untuk mengukur aplikasi kami dengan mudah dan mengelola banyak wadah sebagai satu kesatuan.
    ![GitHub Logo](/minggu-12/Gambar/6.PNG)
    ![GitHub Logo](/minggu-12/Gambar/7.PNG)

### Bagian 4: Skala aplikasi <h3>
Permintaannya gila! Semua orang menyukai aplikasi tidur Anda! Sudah waktunya untuk meningkatkan skala.
    ![GitHub Logo](/minggu-12/Gambar/8.PNG)

Salah satu hal hebat tentang layanan adalah Anda dapat menaikkan dan menurunkannya untuk memenuhi permintaan. Pada langkah ini Anda akan meningkatkan layanan dan kemudian kembali turun.
    ![GitHub Logo](/minggu-12/Gambar/9.PNG)

Anda akan melakukan prosedur berikut dari node1.
    ![GitHub Logo](/minggu-12/Gambar/10.PNG)

Skala jumlah kontainer dalam layanan sleep-app ke 7 dengan pembaruan layanan buruh pelabuhan - replika 7 perintah sleep-app. replika adalah istilah yang kami gunakan untuk menggambarkan wadah identik yang menyediakan layanan yang sama.
    ![GitHub Logo](/minggu-12/Gambar/11.PNG)

### Bagian 5: Kuras simpul dan jadwalkan ulang wadah <h3>
Aplikasi tidur Anda telah melakukan yang luar biasa setelah mencapai Reddit dan HN. Sekarang nomor 1 di App Store! Anda telah meningkatkan selama liburan dan turun selama musim yang lambat. Sekarang Anda sedang melakukan pemeliharaan di salah satu server Anda sehingga Anda harus dengan anggun mengeluarkan server dari kerumunan tanpa mengganggu layanan kepada pelanggan Anda.
    ![GitHub Logo](/minggu-12/Gambar/12.PNG)
    ![GitHub Logo](/minggu-12/Gambar/13.PNG)
    ![GitHub Logo](/minggu-12/Gambar/14.PNG)

Lihatlah status node Anda lagi dengan menjalankan docker node ls pada node1.
    ![GitHub Logo](/minggu-12/Gambar/15.PNG)

### Membersihkan <h3>
Jalankan perintah docker service rm sleep-app pada node1 untuk menghapus layanan yang disebut myservice.
    ![GitHub Logo](/minggu-12/Gambar/16.PNG)
    ![GitHub Logo](/minggu-12/Gambar/17.PNG)