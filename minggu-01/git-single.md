# Installasi <h1>
>Nama   : Achmad Syarif Abdullah                
>NIM    : 175610099
### Windows <h3>

* Setelah download Git, double click pada file yang di-download. Akan dimunculkan lisensi. Klik Next untuk lanjut.
    ![GitHub Logo](/images/1.png)
* Setelah itu, pilih lokasi instalasi. Secara default akan terisi C:\Program Files\Git. Ganti lokasi jika memang anda menginginkan lokasi lain, klik Next
    ![GitHub Logo](/images/2.png)
* Pilih komponen. Tidak perlu diubah-ubah, sesuai dengan default saja. Klik pada Next.
    ![GitHub Logo](/images/3.png)
* Mengisi shortcut untuk menu Start. Gunakan default (Git), ganti jika ingin mengganti - misalnya Git VCS.
    ![GitHub Logo](/images/4.png)
* Pilih editor yang akan digunakan bersama dengan Git. Pada pilihan ini, digunakan Notepad++.
    ![GitHub Logo](/images/5.png)
* Pada saat instalasi, Git menyediakan akses git melalui Bash maupun command prompt. Pilih pilihan kedua supaya bisa menggunakan dari dua antarmuka tersebut. Bash adalah shell di Linux. Dengan menggunakan bash di Windows, pekerjaan di command line Windows bisa dilakukan menggunakan bash - termasuk ekskusi dari Git.
    ![GitHub Logo](/images/6.png)
* Pilih OpenSSL untuk HTTPS. Git menggunakan https untuk akes ke repo GitHub atau repo-repo lain (GitLab, Assembla).
    ![GitHub Logo](/images/7.png)
* Pilih pilihan pertama untuk konversi akhir baris (CR-LF).
    ![GitHub Logo](/images/8.png)
* Pilih PuTTY untuk terminal yang digunakan untuk mengakses Git Bash.
    ![GitHub Logo](/images/9.png)
* Untuk opsi ekstra, pilih serta aktifkan 1 dan 2.
    ![GitHub Logo](/images/10.png)
* Setelah itu proses instalasi akan dilakukan.
    ![GitHub Logo](/images/11.png)
* Jika selesai akan muncul dialog pemberitahuan. Klik pada Finish.
    ![GitHub Logo](/images/12.png)
* Untuk menjalankan, dari Start menu, ketikkan "Git", akan muncul beberapa pilihan. Pilih "Git Bash" atau "Git GUI".
    ![GitHub Logo](/images/13.png)
* Tampilan jika akan menggunakan "Git Bash"
    ![GitHub Logo](/images/14.png)
* Tampilan jika akan menggunakan "Git GUI"
    ![GitHub Logo](/images/15.png)
* Untuk mencoba dari command prompt, masuk ke command prompt, setelah itu eksekusi "git --version" untuk melihat apakah sudah terinstall atau belum. Jika sudah terinstall dengan benar, makan akan muncul hasil berikut:
    ![GitHub Logo](/images/16.png)

### Konfigurasi <h3>

Secara minimal, user harus memberitahu Git tentang username serta email yang digunakan setiap kali terjadi perubahan pada repo Git. Username serta email ini yang akan dimasukkan oleh Git ke catatan perubahan di repo. Di sistem operasi Linux atau sejanis (UNIX), konfigurasi ini nantinya akan disimpan di $HOME/.gitconfig. Untuk sistem operasi Windows, konfigurasi ini akan disimpan di C:\Document and Settings\NamaUser dengan nama file .gitconfig. Secara minimal, ada 2 hal yang perlu dikonfigurasi yaitu username dan email. Gunakan perintah berikut:

Isian di atas harus disesuaikan dengan nama serta email yang digunakan untuk mendaftar di GitHub. Untuk melihat konfigurasi yang sudah ada:


### Mengelola Repo Sendiri <h3>