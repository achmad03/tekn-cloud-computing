# ======= <h1>
> Nama: Achmad Syarif Abdullah
> NIM: 175610099
### ======= <h3>

### Pengaturan Panggung
Mari kita mulai dengan mengkloning repositori kode demo, mengubah direktori kerja, dan memeriksa cabang demo terlebih dahulu.   
    ![GitHub Logo](/minggu-11/Gambar/1.PNG)
    ![GitHub Logo](/minggu-11/Gambar/2.PNG)
### Langkah 0: Skrip Extractor Tautan Dasar <h3>
Periksa cabang step0 dan daftarkan file di dalamnya.   
    ![GitHub Logo](/minggu-11/Gambar/3.PNG)

File linkextractor.py adalah yang menarik di sini, jadi mari kita lihat isinya:
    ![GitHub Logo](/minggu-11/Gambar/4.PNG)
    ![GitHub Logo](/minggu-11/Gambar/5.PNG)

Namun, skrip yang tampaknya sederhana ini mungkin bukan yang paling mudah dijalankan pada mesin yang tidak memenuhi persyaratannya. File README.md menyarankan cara menjalankannya, jadi mari kita coba:

### Langkah 1: Skrip Extractor Tautan Kontainer <h3>
Periksa cabang step1 dan daftarkan file di dalamnya.
    ![GitHub Logo](/minggu-11/Gambar/6.PNG)

Kami telah menambahkan satu file baru (mis., Dockerfile) pada langkah ini. Mari kita lihat isinya:
    ![GitHub Logo](/minggu-11/Gambar/7.PNG)

Sejauh ini, kami baru saja menggambarkan bagaimana kami ingin gambar Docker kami menjadi seperti, tetapi tidak benar-benar membangun satu. Jadi mari kita lakukan itu:
    ![GitHub Logo](/minggu-11/Gambar/8.PNG)

Kami telah membuat gambar Docker bernama linkextractor: step1 berdasarkan Dockerfile yang diilustrasikan di atas. Jika build berhasil, kita harus dapat melihatnya di daftar gambar:
    ![GitHub Logo](/minggu-11/Gambar/9.PNG)

Gambar ini harus memiliki semua bahan yang diperlukan yang dikemas di dalamnya untuk menjalankan skrip di mana saja pada mesin yang mendukung Docker. Sekarang, mari kita jalankan wadah satu kali dengan gambar ini dan ekstrak tautan dari beberapa halaman web langsung:   
    ![GitHub Logo](/minggu-11/Gambar/10.PNG)

### Langkah 2: Tautkan Modul Extractor dengan URI dan Teks Jangkar Penuh <h3>
Periksa cabang step2 dan daftarkan file di dalamnya.

Pada langkah ini skrip linkextractor.py diperbarui dengan perubahan fungsional berikut:
    ![GitHub Logo](/minggu-11/Gambar/11.PNG)

Jalur dinormalisasi ke URL lengkap
Melaporkan tautan dan teks jangkar
Dapat digunakan sebagai modul di skrip lain
Mari kita lihat skrip yang diperbarui:   
    ![GitHub Logo](/minggu-11/Gambar/12.PNG)
    ![GitHub Logo](/minggu-11/Gambar/13.PNG)
    ![GitHub Logo](/minggu-11/Gambar/14.PNG)
    ![GitHub Logo](/minggu-11/Gambar/15.PNG)

### Langkah 3: Tautan Layanan API Extractor <h3>
Periksa cabang step3 dan daftarkan file di dalamnya.
    ![GitHub Logo](/minggu-11/Gambar/16.PNG)
    ![GitHub Logo](/minggu-11/Gambar/17.PNG)

Mari pertama-tama kita melihat Dockerfile untuk melihat perubahan:
    ![GitHub Logo](/minggu-11/Gambar/18.PNG)
    ![GitHub Logo](/minggu-11/Gambar/19.PNG)
    ![GitHub Logo](/minggu-11/Gambar/20.PNG)
    ![GitHub Logo](/minggu-11/Gambar/21.PNG)

### Langkah 4: Link Extractor API dan Layanan Front Web End <h3>
Periksa cabang step4 dan daftarkan file di dalamnya.
    ![GitHub Logo](/minggu-11/Gambar/22.PNG)

Sekarang, mari kita lihat file www / index.php yang menghadap pengguna:
    ![GitHub Logo](/minggu-11/Gambar/23.PNG)

Mari kita naikkan layanan ini dalam mode terpisah menggunakan utilitas pembuatan docker:
    ![GitHub Logo](/minggu-11/Gambar/24.PNG)
    ![GitHub Logo](/minggu-11/Gambar/25.PNG)

Memeriksa daftar kontainer yang berjalan mengonfirmasi bahwa kedua layanan tersebut memang berjalan:
    ![GitHub Logo](/minggu-11/Gambar/26.PNG)
    ![GitHub Logo](/minggu-11/Gambar/27.PNG)