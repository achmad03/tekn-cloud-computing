# ======= <h1>
>Nama   : Achmad Syarif Abdullah                
>NIM    : 175610099
### ======= <h3>

### Deploy the app <h3>

Pada langkah ini Anda akan menyebarkan aplikasi ke Heroku.

Buat aplikasi di Heroku, yang menyiapkan Heroku untuk menerima kode sumber Anda:
     ![GitHub Logo](/minggu-03/Gambar/php/1.PNG)
     ![GitHub Logo](/minggu-03/Gambar/php/2.PNG)

Saat Anda membuat aplikasi, git remote (disebut heroku) juga dibuat dan dikaitkan dengan repositori git lokal Anda.

Heroku menghasilkan nama acak (dalam hal ini sharp-rain-871) untuk aplikasi Anda, atau Anda dapat memberikan parameter untuk menentukan nama aplikasi Anda sendiri.

Sekarang sebarkan kode Anda:    
     ![GitHub Logo](/minggu-03/Gambar/php/3.PNG)
Aplikasi sekarang digunakan. Pastikan setidaknya satu instance aplikasi sedang berjalan:

Sekarang kunjungi aplikasi di URL yang dihasilkan oleh nama aplikasinya. Sebagai pintasan praktis, Anda dapat membuka situs web sebagai berikut:   
     ![GitHub Logo](/minggu-03/Gambar/php/4.PNG)
     ![GitHub Logo](/minggu-03/Gambar/php/31.PNG)

### View logs <h3>
Heroku memperlakukan log sebagai aliran peristiwa yang dipesan waktu yang dikumpulkan dari aliran keluaran semua aplikasi Anda dan komponen Heroku, menyediakan saluran tunggal untuk semua peristiwa.
     ![GitHub Logo](/minggu-03/Gambar/php/5.PNG)

### Scale the app <h3>
Saat ini, aplikasi Anda berjalan pada satu dino web. Pikirkan dyno sebagai wadah ringan yang menjalankan perintah yang ditentukan dalam Procfile.

Anda dapat memeriksa berapa banyak dyno yang berjalan menggunakan perintah ps:
     ![GitHub Logo](/minggu-03/Gambar/php/6.PNG)

Penskalaan aplikasi pada Heroku sama dengan mengubah jumlah dino yang sedang berjalan. Skala jumlah dinamika web menjadi nol:   
     ![GitHub Logo](/minggu-03/Gambar/php/7.PNG)

### Declare app dependencies <h3>
Heroku mengenali aplikasi sebagai PHP dengan adanya file composer.json di direktori root.

Aplikasi demo yang Anda gunakan sudah memiliki composer.json, dan tampilannya seperti ini:
     ![GitHub Logo](/minggu-03/Gambar/php/8.PNG)

### Push local changes <h3>
Pada langkah ini Anda akan belajar bagaimana menyebarkan perubahan lokal ke aplikasi melalui Heroku. Sebagai contoh, Anda akan memodifikasi aplikasi untuk menambahkan ketergantungan tambahan (perpustakaan Cowsay) dan kode untuk menggunakannya.

Pertama, gunakan komposer untuk meminta ketergantungan baru:
     ![GitHub Logo](/minggu-03/Gambar/php/9.PNG)

Ini juga akan mengubah composer.json. Jika Anda memperkenalkan ketergantungan dengan memodifikasi sendiri file composer.json, pastikan untuk memperbarui dependensi dengan menjalankan:
     ![GitHub Logo](/minggu-03/Gambar/php/10.PNG)

Ketika rute itu dikunjungi, itu akan membuat seekor sapi yang cantik.
     ![GitHub Logo](/minggu-03/Gambar/php/11.PNG)

Sekarang gunakan. Hampir setiap penyebaran ke Heroku mengikuti pola yang sama.

Pertama, tambahkan file yang dimodifikasi ke repositori git lokal:
     ![GitHub Logo](/minggu-03/Gambar/php/12.PNG)
     ![GitHub Logo](/minggu-03/Gambar/php/32.PNG)

### Start an interactive shell <h3>
Anda dapat menjalankan perintah, biasanya skrip dan aplikasi yang merupakan bagian dari aplikasi Anda, dalam satu dino menggunakan perintah heroku run. Itu juga dapat digunakan untuk meluncurkan shell PHP interaktif yang terpasang pada terminal lokal Anda untuk bereksperimen di lingkungan aplikasi Anda:   
     ![GitHub Logo](/minggu-03/Gambar/php/13.PNG)   
     ![GitHub Logo](/minggu-03/Gambar/php/14.PNG)

### Define config vars <h3>
Heroku memungkinkan Anda melakukan eksternalisasi konfigurasi - menyimpan data seperti kunci enkripsi atau alamat sumber daya eksternal dalam konfigurasi.

Saat runtime, config vars diekspos sebagai variabel lingkungan ke aplikasi.
     ![GitHub Logo](/minggu-03/Gambar/php/15.PNG)

Ubah web / index.php sehingga rute root mengembalikan kata Halo yang diulang dengan nilai variabel lingkungan TIMES:
     ![GitHub Logo](/minggu-03/Gambar/php/16.PNG)