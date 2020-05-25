# ======= <h1>
>Nama   : Achmad Syarif Abdullah                
>NIM    : 175610099
### ======= <h3>

### Isikan file utils/res.go <h3>

utils/res.go
    ![GitHub Logo](/minggu-06/Gambar/mysql/1.PNG)

Kode di atas berguna untuk menampilkan data dengan bentuk JSON di browser. Fungsi di atas nantinya akan kita panggil dari file main.go.

### Isikan file models/mahasiswa.go <h3>
Sekarang kita buat modelnya, silahkan buka models/mahasiswa.go.
    ![GitHub Logo](/minggu-06/Gambar/mysql/2.PNG)
models/mahasiswa.go

### Koneksi Golang ke Database MySQL <h3>
Sebelumnya silahkan buat database dengan nama akademik. Dan nama tabel mahasiswa.
    ![GitHub Logo](/minggu-06/Gambar/mysql/3.PNG)

Jika sudah, sekarang mari kita buat kode nya. Untuk melakukan koneksi dengan database MySQL kita menggunakan file config/config.go.

### Membuat Routing dan Method <h3>
Silahkan buka lagi file main.go nya, kita akan membuat method dan routing.
    ![GitHub Logo](/minggu-06/Gambar/mysql/4.PNG)

        
    package main

    import (
        "context"
        "fmt"
        "minggu-06/mahasiswa"
        "minggu-06/utils"
        "log"
        "net/http"
    )

    func main() {

        http.HandleFunc("/mahasiswa1", GetMahasiswa)
        err := http.ListenAndServe(":7000", nil)

        if err != nil {
            log.Fatal(err)
        }
    }

    // GetMahasiswa
    func GetMahasiswa(w http.ResponseWriter, r *http.Request) {
        if r.Method == "GET" {
            ctx, cancel := context.WithCancel(context.Background())

            defer cancel()

            mahasiswas, err := mahasiswa.GetAll(ctx)

            if err != nil {
                fmt.Println(err)
            }

            utils.ResponseJSON(w, mahasiswas, http.StatusOK)
            return
        }

        http.Error(w, "Tidak di ijinkan", http.StatusNotFound)
        return
    }

        

### Query Menampilkan Data dari Database MySQL dengan Golang <h3>
Silahkan buka file mahasiswa/repository_mysql.go.
    ![GitHub Logo](/minggu-06/Gambar/mysql/5.PNG)

