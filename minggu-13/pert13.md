# ======= <h1>
> Nama: Achmad Syarif Abdullah
> NIM: 175610099
### ======= <h3>

### Cluster dan jalankan <h3>
Kami sudah menginstal minikube untuk Anda. Periksa apakah sudah diinstal dengan benar, dengan menjalankan perintah versi minikube:   
    ![GitHub Logo](/minggu-13/Gambar/1.PNG)

OK, kita bisa melihat bahwa minikube sudah ada.

Mulai cluster, dengan menjalankan perintah mulai minikube:
    ![GitHub Logo](/minggu-13/Gambar/2.PNG)

Bagus! Anda sekarang memiliki kluster Kubernetes yang sedang berjalan di terminal online Anda. Minikube memulai mesin virtual untuk Anda, dan cluster Kubernetes sekarang berjalan di VM itu.

### Versi klaster <h3>
Untuk berinteraksi dengan Kubernet selama bootcamp ini, kami akan menggunakan antarmuka baris perintah, kubectl. Kami akan menjelaskan kubectl secara terperinci dalam modul berikutnya, tetapi untuk sekarang, kami hanya akan melihat beberapa informasi klaster. Untuk memeriksa apakah kubectl diinstal, Anda dapat menjalankan perintah versi kubectl:
    ![GitHub Logo](/minggu-13/Gambar/3.PNG)



OK, kubectl sudah dikonfigurasi dan kita bisa melihat versi klien dan juga server. Versi klien adalah versi kubectl; versi server adalah versi Kubernet yang diinstal pada master. Anda juga dapat melihat detail tentang pembuatan.

### Detail klaster <h3>
Mari kita lihat detail cluster. Kami akan melakukannya dengan menjalankan Kubectl-info:
    ![GitHub Logo](/minggu-13/Gambar/4.PNG)



Selama tutorial ini, kami akan berfokus pada baris perintah untuk menggunakan dan menjelajahi aplikasi kami. Untuk melihat node di cluster, jalankan perintah kubectl get node:   
    ![GitHub Logo](/minggu-13/Gambar/5.PNG)



Perintah ini menunjukkan semua node yang dapat digunakan untuk meng-host aplikasi kita. Sekarang kami hanya memiliki satu simpul, dan kami dapat melihat bahwa statusnya siap (siap menerima aplikasi untuk ditempatkan).

### dasar-dasar kubectl <h3>
Seperti minikube, kubectl dipasang di terminal online. Ketik kubectl di terminal untuk melihat penggunaannya. Format umum dari perintah kubectl adalah: kubectl action resource. Ini melakukan tindakan yang ditentukan (seperti membuat, menjelaskan) pada sumber daya yang ditentukan (seperti simpul, wadah). Anda dapat menggunakan --help setelah perintah untuk mendapatkan info tambahan tentang kemungkinan parameter (kubectl get nodes --help).

Periksa apakah kubectl dikonfigurasikan untuk berbicara dengan kluster Anda, dengan menjalankan perintah versi kubectl:
    ![GitHub Logo](/minggu-13/Gambar/6.PNG)

OK, kubectl diinstal dan Anda dapat melihat versi klien dan server.

Untuk melihat node di cluster, jalankan perintah kubectl get node:   
    ![GitHub Logo](/minggu-13/Gambar/7.PNG)

Di sini kita melihat node yang tersedia (1 dalam kasus kami). Kubernetes akan memilih tempat untuk menyebarkan aplikasi kami berdasarkan sumber daya Node yang tersedia.

### Menyebarkan aplikasi kami <h3>
Mari kita gunakan aplikasi pertama kita di Kubernetes dengan kubectl create command deployment. Kami perlu memberikan nama penyebaran dan lokasi gambar aplikasi (termasuk url repositori lengkap untuk gambar yang dihosting di luar hub Docker).

kubectl membuat penyebaran kubernetes-bootcamp --image = gcr.io / google-samples / kubernetes-bootcamp: v1

Bagus! Anda baru saja menggunakan aplikasi pertama Anda dengan membuat penyebaran. Ini melakukan beberapa hal untuk Anda:   
    ![GitHub Logo](/minggu-13/Gambar/8.PNG)

mencari simpul yang cocok di mana instance aplikasi dapat dijalankan (kami hanya memiliki 1 node yang tersedia)
menjadwalkan aplikasi untuk berjalan di Node itu
mengkonfigurasi cluster untuk menjadwal ulang instance pada Node baru bila diperlukan
Untuk daftar penyebaran Anda gunakan perintah get penyebaran:
    ![GitHub Logo](/minggu-13/Gambar/9.PNG)

Kami melihat bahwa ada 1 penyebaran yang menjalankan satu instance aplikasi Anda. Mesin virtual dijalankan di dalam wadah Docker di simpul Anda.

### Lihat aplikasi kami <h3>
Pod yang berjalan di dalam Kubernetes berjalan di jaringan pribadi yang terisolasi. Secara default mereka terlihat dari pod dan layanan lain di dalam cluster kubernetes yang sama, tetapi tidak di luar jaringan itu. Ketika kami menggunakan kubectl, kami berinteraksi melalui titik akhir API untuk berkomunikasi dengan aplikasi kami.

Kami akan membahas opsi lain tentang cara mengekspos aplikasi Anda di luar cluster kubernetes di Modul 4.
    ![GitHub Logo](/minggu-13/Gambar/10.PNG)

Perintah kubectl dapat membuat proksi yang akan meneruskan komunikasi ke dalam jaringan privat cluster-wide. Proxy dapat diakhiri dengan menekan control-C dan tidak akan menampilkan output apa pun saat sedang berjalan.

Kami akan membuka jendela terminal kedua untuk menjalankan proxy.

echo -e "\ n \ n \ n \ e [92mulai Proxy. Setelah memulai tidak akan menghasilkan respons. Silakan klik Terminal Terminal pertama \ n";
proksi kubectl
Kami sekarang memiliki koneksi antara host kami (terminal online) dan kluster Kubernetes. Proxy memungkinkan akses langsung ke API dari terminal ini.

Anda dapat melihat semua API yang dihosting melalui titik akhir proxy. Misalnya, kami dapat meminta versi langsung melalui API menggunakan perintah curl:   
    ![GitHub Logo](/minggu-13/Gambar/11.PNG)

Jika Port 8001 tidak dapat diakses, pastikan bahwa proksi kubectl yang dimulai di atas berjalan.

Server API akan secara otomatis membuat titik akhir untuk setiap pod, berdasarkan nama pod, yang juga dapat diakses melalui proxy.

Pertama kita perlu mendapatkan nama Pod, dan kami akan menyimpan di variabel lingkungan POD_NAME:

export POD_NAME = $ (kubectl dapatkan pod -o-templat --template '{{range .items}} {{. metadata.name}} {{"\ n"}} {{end}}')
echo Name of the Pod: $ POD_NAME

Catatan: Periksa bagian atas terminal. Proxy dijalankan di tab baru (Terminal 2), dan perintah terbaru dijalankan pada tab asli (Terminal 1). Proxy masih berjalan di tab kedua, dan ini memungkinkan perintah curl kami untuk bekerja menggunakan localhost: 8001.   
    ![GitHub Logo](/minggu-13/Gambar/12.PNG)

Agar penyebaran baru dapat diakses tanpa menggunakan Proxy, Layanan diperlukan yang akan dijelaskan dalam modul berikutnya.