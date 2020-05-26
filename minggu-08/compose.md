# ======= <h1>
>Nama   : Achmad Syarif Abdullah                
>NIM    : 175610099
### ======= <h3>

### Prasyarat <h3>
Pastikan Anda sudah menginstal Docker Engine dan Docker Compose. Anda tidak perlu menginstal Python atau Redis, karena keduanya disediakan oleh gambar Docker.

### Langkah 1: Atur <h3>
Tentukan dependensi aplikasi.
* Buat direktori untuk proyek:   
    ![GitHub Logo](/minggu-08/Gambar/1.PNG)

* Buat file bernama app.py di direktori proyek Anda dan rekatkan di:
    ![GitHub Logo](/minggu-08/Gambar/2.PNG)
    
* Buat file lain yang disebut requirement.txt di direktori proyek Anda dan tempel ini di:   
    ![GitHub Logo](/minggu-08/Gambar/3.PNG)

### Langkah 2: Buat Dockerfile <h3>
Pada langkah ini, Anda menulis Dockerfile yang membuat gambar Docker. Gambar berisi semua dependensi yang dibutuhkan aplikasi Python, termasuk Python itu sendiri.

* Di direktori proyek Anda, buat file bernama Dockerfile dan rekatkan yang berikut ini:
    ![GitHub Logo](/minggu-08/Gambar/4.PNG)

### Langkah 3: Tentukan layanan dalam file Tulis <h3>
Buat file bernama docker-compose.yml di direktori proyek Anda dan rekatkan yang berikut ini:
    ![GitHub Logo](/minggu-08/Gambar/5.PNG)

### Langkah 4: Bangun dan jalankan aplikasi Anda dengan Compose <h3>
* Dari direktori proyek Anda, jalankan aplikasi Anda dengan menjalankan docker-compose up.
    ![GitHub Logo](/minggu-08/Gambar/6.PNG)

* Masukkan http: // localhost: 5000 / di browser untuk melihat aplikasi berjalan.
    ![GitHub Logo](/minggu-08/Gambar/7.PNG)