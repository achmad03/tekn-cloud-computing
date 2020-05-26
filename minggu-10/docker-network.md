# ======= <h1>
> Nama: Achmad Syarif Abdullah
> NIM: 175610099
### ======= <h3>

### Langkah 1: Perintah Jaringan Docker <h3>
Perintah jaringan buruh pelabuhan adalah perintah utama untuk mengonfigurasi dan mengelola jaringan kontainer. Jalankan perintah jaringan buruh pelabuhan dari terminal pertama.
    ![GitHub Logo](/minggu-10/Gambar/1.PNG)  
### Langkah 2: Daftar jaringan <h3>
Jalankan jaringan buruh pelabuhan ls perintah untuk melihat jaringan kontainer yang ada pada host Docker saat ini.
    ![GitHub Logo](/minggu-10/Gambar/2.PNG)  
### Langkah 3: Periksa jaringan <h3>
Perintah inspeksi jaringan buruh pelabuhan digunakan untuk melihat detail konfigurasi jaringan. Rincian ini meliputi; nama, ID, driver, driver IPAM, info subnet, wadah terhubung, dan banyak lagi.
    ![GitHub Logo](/minggu-10/Gambar/3.PNG)  
Gunakan jaringan docker periksa <network> untuk melihat detail konfigurasi dari jaringan kontainer pada host Docker Anda. Perintah di bawah ini menunjukkan rincian jaringan yang disebut jembatan.

### Langkah 4: Daftar plugin driver jaringan <h3>
Perintah info buruh pelabuhan menunjukkan banyak informasi menarik tentang pemasangan Docker.
    ![GitHub Logo](/minggu-10/Gambar/4.PNG)  
Jalankan perintah info buruh pelabuhan dan temukan daftar plugin jaringan.

### Bagian # 2 - Jembatan Jaringan
### Langkah 1: Dasar-Dasarnya <h3>
Setiap instalasi Docker yang bersih dilengkapi dengan jaringan yang disebut jembatan. Verifikasi ini dengan jaringan buruh pelabuhan ls.
    ![GitHub Logo](/minggu-10/Gambar/5.PNG)  
Semua jaringan yang dibuat dengan driver jembatan didasarkan pada Linux bridge (a.k.a. switch virtual).
    ![GitHub Logo](/minggu-10/Gambar/6.PNG)  
Instal perintah brctl dan gunakan untuk mendaftar jembatan Linux di host Docker Anda. Anda dapat melakukan ini dengan menjalankan sudo apt-get install bridge-utils.
    ![GitHub Logo](/minggu-10/Gambar/7.PNG)  
    ![GitHub Logo](/minggu-10/Gambar/8.PNG)  
    ![GitHub Logo](/minggu-10/Gambar/9.PNG)  
### Langkah 2: Hubungkan wadah <h3>
Jaringan jembatan adalah jaringan default untuk wadah baru. Ini berarti bahwa kecuali Anda menentukan jaringan yang berbeda, semua kontainer baru akan terhubung ke jaringan jembatan.
    ![GitHub Logo](/minggu-10/Gambar/10.PNG)  
Buat wadah baru dengan menjalankan docker run -dt ubuntu sleep infinity.
    ![GitHub Logo](/minggu-10/Gambar/11.PNG)  
Perintah ini akan membuat wadah baru berdasarkan ubuntu: gambar terbaru dan akan menjalankan perintah tidur untuk menjaga wadah tetap berjalan di latar belakang. Anda dapat memverifikasi wadah contoh kami sudah habis dengan menjalankan buruh pelabuhan ps.
    ![GitHub Logo](/minggu-10/Gambar/12.PNG)  
    ![GitHub Logo](/minggu-10/Gambar/13.PNG)  
### Langkah 3: Uji konektivitas jaringan <h3>
Output ke perintah inspeksi jaringan buruh pelabuhan sebelumnya menunjukkan alamat IP wadah baru. Dalam contoh sebelumnya ini adalah "172.17.0.2" tetapi milik Anda mungkin berbeda. 
    ![GitHub Logo](/minggu-10/Gambar/14.PNG)  
Ping alamat IP wadah dari prompt shell host Docker Anda dengan menjalankan ping -c5 <Alamat IPv4>. Ingatlah untuk menggunakan IP wadah di lingkungan Anda.    
Pertama, kita perlu mendapatkan ID wadah dimulai pada langkah sebelumnya. Anda dapat menjalankan buruh pelabuhan ps untuk mendapatkan itu.    
Selanjutnya, kita perlu menginstal program ping. Jadi, mari kita jalankan pembaruan apt-get && apt-get install -y iputils-ping.
    ![GitHub Logo](/minggu-10/Gambar/15.PNG)  
    ![GitHub Logo](/minggu-10/Gambar/16.PNG)  
### Langkah 4: Konfigurasikan NAT untuk konektivitas eksternal <h3>
Dalam langkah ini kami akan memulai wadah NGINX baru dan memetakan port 8080 pada host Docker ke port 80 di dalam wadah. Ini berarti bahwa lalu lintas yang mengenai host Docker di port 8080 akan diteruskan ke port 80 di dalam wadah.

Mulai wadah baru berdasarkan gambar NGINX resmi dengan menjalankan docker run --name web1 -d -p 8080: 80 nginx.
    ![GitHub Logo](/minggu-10/Gambar/17.PNG)  
Jika karena alasan tertentu Anda tidak dapat membuka sesi dari web broswer, Anda dapat terhubung dari host Docker Anda menggunakan perintah curl 127.0.0.1:8080.
    ![GitHub Logo](/minggu-10/Gambar/18.PNG)  