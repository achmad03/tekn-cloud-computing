# ======= <h1>
>Nama   : Achmad Syarif Abdullah                
>NIM    : 175610099
### ======= <h3>

### Import <h3>
import library   
    ![GitHub Logo](/minggu-06/Gambar/mongo/1.PNG)   
        
    package main

    import (
        "context"
        "encoding/json"
        "fmt"
        "net/http"
        "time"
        "github.com/gorilla/mux"
        "go.mongodb.org/mongo-driver/bson"
        "go.mongodb.org/mongo-driver/bson/primitive"
        "go.mongodb.org/mongo-driver/mongo"
        "go.mongodb.org/mongo-driver/mongo/options"
    )

### Koneksi <h3>
buat koneksi ke mongo   
    ![GitHub Logo](/minggu-06/Gambar/mongo/3.PNG)   
        
    func main() {
        fmt.Println("Starting the application...")
        ctx, _ := context.WithTimeout(context.Background(), 10*time.Second)
        clientOptions := options.Client().ApplyURI("mongodb://localhost:27017")
        client, _ = mongo.Connect(ctx, clientOptions)
        router := mux.NewRouter()
        router.HandleFunc("/people", GetPeopleEndpoint).Methods("GET")
        http.ListenAndServe(":12345", router)
    }

### Model <h3>
buat model data   
    ![GitHub Logo](/minggu-06/Gambar/mongo/2.PNG)   

        
    var client *mongo.Client

    type Person struct {
            ID        primitive.ObjectID       `json:"_id,omitempty" bson:"_id,omitempty"`
            NIM       string       `json:"nim,omitempty" bson:"nim,omitempty"`
            Name      string    `json:"name,omitempty" bson:"name,omitempty"`
            Semester  string    `json:"semester,omitempty" bson:"semester,omitempty"`
        
    }

### Query <h3>
buat query data   
    ![GitHub Logo](/minggu-06/Gambar/mongo/4.PNG)   
    ![GitHub Logo](/minggu-06/Gambar/mongo/5.PNG)   

        
    func GetPeopleEndpoint(response http.ResponseWriter, request *http.Request) {
        response.Header().Add("content-type", "application/json")
        var people []Person
        collection := client.Database("akademik").Collection("mahasiswa")
        ctx, _ := context.WithTimeout(context.Background(), 30*time.Second)
        cursor, err := collection.Find(ctx, bson.M{})
        if err != nil {
            response.WriteHeader(http.StatusInternalServerError)
            response.Write([]byte(`{ "message": "` + err.Error() + `" }`))
            return
        }
        defer cursor.Close(ctx)
        for cursor.Next(ctx) {
            var person Person
            cursor.Decode(&person)
            people = append(people, person)
        }
        if err := cursor.Err(); err != nil {
            response.WriteHeader(http.StatusInternalServerError)
            response.Write([]byte(`{ "message": "` + err.Error() + `" }`))
            return
        }
        json.NewEncoder(response).Encode(people)
    }


