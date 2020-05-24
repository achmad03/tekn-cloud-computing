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

Isian di atas harus disesuaikan dengan nama serta email yang digunakan untuk mendaftar di GitHub. Untuk melihat konfigurasi yang sudah ada:


### Mengelola Repo Sendiri <h3>