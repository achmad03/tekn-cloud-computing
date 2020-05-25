# ======= <h1>
>Nama   : Achmad Syarif Abdullah                
>NIM    : 175610099
### ======= <h3>

### Isikan file utils/res.go <h3>

utils/res.go   
    ![GitHub Logo](/minggu-06/Gambar/mysql/1.PNG)

        
    package utils

    import (
        "encoding/json"
        "net/http"
    )

    func ResponseJSON(w http.ResponseWriter, p interface{}, status int) {
        ubahkeByte, err := json.Marshal(p)

        w.Header().Set("Content-Type", "application/json")

        if err != nil {
            http.Error(w, "error om", http.StatusBadRequest)
        }

        w.Header().Set("Content-Type", "application/json")
        w.WriteHeader(status)
        w.Write([]byte(ubahkeByte))
    }


Kode di atas berguna untuk menampilkan data dengan bentuk JSON di browser. Fungsi di atas nantinya akan kita panggil dari file main.go.

### Isikan file models/mahasiswa.go <h3>
Sekarang kita buat modelnya, silahkan buka models/mahasiswa.go.   
    ![GitHub Logo](/minggu-06/Gambar/mysql/2.PNG)   
    ![GitHub Logo](/minggu-06/Gambar/mysql/7.PNG)

        
    package models

    import (
        "time"
    )

    type (
        // Mahasiswa
        Mahasiswa struct {
            ID        int       `json:"id"`
            NIM       int       `json:"nim"`
            Name      string    `name:"name"`
            Semester  string       `json:"semester"`
            CreatedAt time.Time `json:"created_at"`
            UpdatedAt time.Time `json:"updated_at"`
        }
    )


models/mahasiswa.go

### Koneksi Golang ke Database MySQL <h3>
Sebelumnya silahkan buat database dengan nama akademik. Dan nama tabel mahasiswa.   
    ![GitHub Logo](/minggu-06/Gambar/mysql/3.PNG)

        
    package config

    import (
        "database/sql"
        "fmt"
        _ "mysql-master"
    )

    const (
        username string = "root"
        password string = ""
        database string = "akademik"
    )

    var (
        dsn = fmt.Sprintf("%v:%v@/%v", username, password, database)
    )

    // HubToMySQL
    func MySQL() (*sql.DB, error) {
        db, err := sql.Open("mysql", dsn)

        if err != nil {
            return nil, err
        }

        return db, nil
    }


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
    ![GitHub Logo](/minggu-06/Gambar/mysql/6.PNG)

        
    package mahasiswa

    import (
        "context"
        "fmt"
        "minggu-06/config"
        "minggu-06/models"
        "log"
        "time"
    )

    const (
        table          = "mahasiswa"
        layoutDateTime = "2006-01-02 15:04:05"
    )

    // GetAll
    func GetAll(ctx context.Context) ([]models.Mahasiswa, error) {

        var mahasiswas []models.Mahasiswa

        db, err := config.MySQL()

        if err != nil {
            log.Fatal("Cant connect to MySQL", err)
        }

        queryText := fmt.Sprintf("SELECT * FROM %v Order By id DESC", table)

        rowQuery, err := db.QueryContext(ctx, queryText)

        if err != nil {
            log.Fatal(err)
        }

        for rowQuery.Next() {
            var mahasiswa models.Mahasiswa
            var createdAt, updatedAt string

            if err = rowQuery.Scan(&mahasiswa.ID,
                &mahasiswa.NIM,
                &mahasiswa.Name,
                &mahasiswa.Semester,
                &createdAt,
                &updatedAt); err != nil {
                return nil, err
            }

            //  Change format string to datetime for created_at and updated_at
            mahasiswa.CreatedAt, err = time.Parse(layoutDateTime, createdAt)

            if err != nil {
                log.Fatal(err)
            }

            mahasiswa.UpdatedAt, err = time.Parse(layoutDateTime, updatedAt)

            if err != nil {
                log.Fatal(err)
            }

            mahasiswas = append(mahasiswas, mahasiswa)
        }

        return mahasiswas, nil
    }
