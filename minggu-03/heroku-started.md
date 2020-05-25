# ======= <h1>
>Nama   : Achmad Syarif Abdullah                
>NIM    : 175610099
### ======= <h3>

### Prepare the app <h3>
Pada langkah ini, Anda akan menyiapkan aplikasi sederhana yang dapat digunakan.
    ![GitHub Logo](/minggu-03/Gambar/1.PNG)
Untuk mengkloning aplikasi sampel sehingga Anda memiliki versi lokal dari kode yang kemudian dapat Anda terapkan ke Heroku, jalankan perintah berikut di shell perintah atau terminal lokal Anda:


### Deploy the app <h3>
Pada langkah ini Anda akan menyebarkan aplikasi ke Heroku.

Buat aplikasi di Heroku, yang menyiapkan Heroku untuk menerima kode sumber Anda:
    ![GitHub Logo](/minggu-03/Gambar/2.PNG)   
Sekarang sebarkan kode Anda:   
    ![GitHub Logo](/minggu-03/Gambar/3.PNG)
Aplikasi sekarang digunakan. Pastikan setidaknya satu instance aplikasi sedang berjalan:
    ![GitHub Logo](/minggu-03/Gambar/4.PNG)
Sekarang kunjungi aplikasi di URL yang dihasilkan oleh nama aplikasinya. Sebagai pintasan praktis, Anda dapat membuka situs web sebagai berikut:   
    ![GitHub Logo](/minggu-03/Gambar/5.PNG)
    ![GitHub Logo](/minggu-03/Gambar/05.PNG)

### View logs <h3>
Heroku memperlakukan log sebagai aliran peristiwa yang dipesan waktu yang dikumpulkan dari aliran keluaran semua aplikasi Anda dan komponen Heroku, menyediakan saluran tunggal untuk semua peristiwa.
    ![GitHub Logo](/minggu-03/Gambar/6.PNG)

### Define a Procfile <h3>
Heroku memperlakukan log sebagai aliran peristiwa yang dipesan waktu yang dikumpulkan dari aliran keluaran semua aplikasi Anda dan komponen Heroku, menyediakan saluran tunggal untuk semua jendela.

### Scale the app <h3>
Saat ini, aplikasi Anda berjalan pada satu dino web. Pikirkan dyno sebagai wadah ringan yang menjalankan perintah yang ditentukan dalam Procfile.
    ![GitHub Logo](/minggu-03/Gambar/7.PNG)
    ![GitHub Logo](/minggu-03/Gambar/8.PNG)

### Declare app dependencies <h3>

Heroku mengenali aplikasi sebagai aplikasi Python dengan mencari file-file utama. Menyertakan requirement.txt dalam direktori root adalah salah satu cara bagi Heroku untuk mengenali aplikasi Python Anda.
    ![GitHub Logo](/minggu-03/Gambar/9.PNG)
    ![GitHub Logo](/minggu-03/Gambar/10.PNG)
    ![GitHub Logo](/minggu-03/Gambar/11.PNG)

### Run the app locally <h3>
Aplikasi ini hampir siap untuk memulai secara lokal. Django menggunakan aset lokal, jadi pertama-tama, Anda harus menjalankan collstatic:

Sekarang mulai aplikasi Anda secara lokal menggunakan heroku lokal, yang diinstal sebagai bagian dari Heroku CLI.

Jika Anda menggunakan sistem Microsoft Windows, jalankan ini:
    ![GitHub Logo](/minggu-03/Gambar/12.PNG)

### Push local changes <h3>
Pada langkah ini Anda akan belajar bagaimana menyebarkan perubahan lokal ke aplikasi melalui Heroku. Sebagai contoh, Anda akan memodifikasi aplikasi untuk menambahkan ketergantungan tambahan dan kode untuk menggunakannya.

Install requests locally:
    ![GitHub Logo](/minggu-03/Gambar/14.PNG)
    ![GitHub Logo](/minggu-03/Gambar/15.PNG)   
    ![GitHub Logo](/minggu-03/Gambar/17.PNG)      
### Deploy changes <h3>
Deploy hasil edit    
    ![GitHub Logo](/minggu-03/Gambar/16.PNG)

### Provision add-ons <h3>
Add-on adalah layanan cloud pihak ketiga yang menyediakan layanan tambahan out-of-the-box untuk aplikasi Anda, dari kegigihan hingga pencatatan hingga pemantauan dan banyak lagi.

### Start a console <h3>
Anda dapat menjalankan perintah, biasanya skrip dan aplikasi yang merupakan bagian dari aplikasi Anda, dalam satu dino menggunakan perintah heroku run. Itu juga dapat digunakan untuk meluncurkan proses REPL yang melekat pada terminal lokal Anda untuk bereksperimen di lingkungan aplikasi Anda:
    ![GitHub Logo](/minggu-03/Gambar/18.PNG)
    ![GitHub Logo](/minggu-03/Gambar/19.PNG)

### Define config vars <h3>
Heroku memungkinkan Anda melakukan eksternalisasi konfigurasi - menyimpan data seperti kunci enkripsi atau alamat sumber daya eksternal dalam konfigurasi.   
    ![GitHub Logo](/minggu-03/Gambar/20.PNG)
    ![GitHub Logo](/minggu-03/Gambar/21.PNG)
