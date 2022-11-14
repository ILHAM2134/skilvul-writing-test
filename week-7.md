# Sequelize practice

-   menginstall sequelize untuk mysql

```
npm install --save sequelize

npm install --save mysql2
```

-   connect ke database

```
const Sequelize = require('sequelize')

const sequelize = new Sequelize('sqlite::memory')
```

-   mengecek connection

```
try {
    await sequelize.authenticate()
    console.log('connection has been established successfully')
} catch (error) {
    console.error('unable to connect to the database : ', error)
}
```

-   menutup connection

```
sequelize.close()
```

# MongoDB

## MongoDB intro

-   database terbagi kedalam 2 bentuk, yaitu SQL dan NoSQL, MongoDB merupakan salah satu database NoSQL

-   NoSQL bisa mengolah database dengan fleksibel dan tidak membutuhkan Query

-   kelebihan NoSQL :

    -   Sistem tidak membutuhkan tabel yang terstruktur

    -   By Default sudah menggunakan JSON(JavaScript Object Notation), sehingga memudahkan integrasi dengan JavaScript

    -   Performa lebih cepat dengan kemampuan menampung banyak data yang bervariasi

-   kekurangan NoSQL :

    -   Tidak mendukung transaksi

    -   Masalah konsistensi data

    -   Menggunakan banyak memory

    -   Hanya bisa menampung maksimal 16MB disetiap document

-   MongoDB sering dipakai untuk aplikasi berbasis cloud, big data, maupun grid computing

![struktur-data-MongoDB](./assets/week-7/1.struktur-db-MongoDB "struktur-data-MongoDB")

-   MongoDB menggunakan format JSON

-   Document adalah unit terkecil yang berada pada MongoDB

-   contoh data pada MongoBD
    ![contoh-data-MongoDB](./assets/week-7/2.contoh-data-pada-MongoDB "contoh-data-MongoDB")

-   instalasi MongoDB pada Linux

```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA316203348075D9DCB49F368818C72E5252904

wget -q0 - https://www.mongodb.org/static/pgp/server-4.2.asc | sudo apt-key add -multiverse  | sudo tee /etc/apt/source.list.d/mongodb-org-4.2.list

sudo apt-get update

sudo apt-get install -y mongodb-org

sudo mkdir -p /data/db

sudo chmod 777 /data

sudo chmod 777 /data/db
```

-   command memulai pada mongodb

```
sudo service mongod start

sudo service mongod stop

sudo service mongod restart
```

## Menggunakan MongoDB

-   menggunakan mongo bisa disertai tampilan (GUI), sehingga mempermudah penggunaan, contoh MongoDB GUI yg populer adalah Compass

-   sebelum menggunakan mongo, terlebih dulu mengetikkan 'mongo' pada terminal

```
mongo
```

-   untuk melihat daftar database, digunakan command

```
show dbs
```

-   untuk menggunakan database, gunakan command

```
use <nama-db>
```

-   untuk menambahkan collection baru, digunakan command

```
'db.createCollections('nama-collection')`
```

-   untuk menambah data pada collection, bisa menggunakan command

```
db.namaDB.insert({
    attr1: "value1",
    attr2: "value2"
})
```

-   untuk melihat data yg telah ditambahkan, digunakan command

```
db.namaBD.find()
```

-   untuk update data pada collections, bisa menggunakan command

```
db.namaDB.update({
    'attr1':'value1'
},{
    $set:{'attr3':'value3'}
})
```

-   menghapus data pada collections

```
db.namaBD.remove({'attr1':'value1'})
```

## Mendesain scema MongoDB

-   Jika kita mendesain schema aplikasi MongoDB kita sama dengan mendesain SQL maka kita akan banyak kehilangan fitur MongoDB. Karena MongoDB Tidak ada Formal Process, Tidak ada algorithms, Tidak ada aturan

-   Sebuah MongoDB schema desain yang baik akan memperhatikan Bagaimana kita menstore data Menghasilkan perfoma Query yang bagus

-   Dalam mendesain MongoDB kita ada 2 pendekatan yaitu Embedding dan Referencing

-   Embedding : memasukan semua data yang terkait dalam satu dokumen.

    -   kelebihan :

        -   Bisa mendapatkan semua data dalam 1 query
        -   Bisa mengupdate semua informasi terkait dalam 1 atomic operation
        -   Bisa menggunakan trasaksi operator

    -   kekurangan :
        -   kita tidak memiliki cara untuk dapat mengaksess embended data sebagai entity yang terpisah secara langsung.
        -   Memiliki batasan 16 MB document size

```
{
    id: '12345',
    personal_detail: {
        name: 'skilvul',
        tanggal_lahir:'2000-01-01'
    },
    contact: {
        email: 'silvul@gmail.com',
        phone: '08121657293'
    }
}
```

-   Referencing : memasukan data sebagian saja, tidak keseluruhan.

    -   kelebihan

        -   Bisa mendapatkan semua data dalam 1 query
        -   Bisa mengupdate semua informasi terkait dalam 1 atomic operation
        -   Bisa menggunakan trasaksi operator

    -   kekurangan

    -   kita tidak memiliki cara untuk dapat mengaksess embended data sebagai entity yang terpisah secara langsung.
    -   Memiliki batasan 16 MB document size

```
{
    id: '12345',
    personal_detail: {
        name: 'skilvul',
        tanggal_lahir: '2000-7-08'
    },
    contact: {
        email: 'skilvul@gmail.com,
        phone: '08129127328'
    },
    riwayat_lagu: [
        ObjectID('1213'),
        ObjectID('1263'),
        ObjectID('1243'),
        ObjectID('1219')
    ]
}
```

-   relasi dlm mongodb

    -   one-to-one relationship (disarankan embedded)

    ```
    {
        id: `232324',
        personal_detail: {
            name: 'skilvul',
            tanggal_lahir: '2000-9-12'
        },
        contact: {
            email: 'skilvul@gmail.com',
            phone: '0812475884'
        },
        detail_membership: {
            'number': '1233448732',
            'mulai_mendaftar': '2022-9-21',
            'kadaluarsa': '2023-9-21'
        }
    }
    ```

    -   one to many relationship (disarankan references)

    ```
    {
        id: `232324',
        personal_detail: {
            name: 'skilvul',
            tanggal_lahir: '2000-9-12'
        },
        contact: {
            email: 'skilvul@gmail.com',
            phone: '0812475884'
        },
        riwayat_lagu: {
            ObjectID('1234'),
            ObjectID('1231'),
            ObjectID('1244'),
            ObjectID('4231')
        }
    }
    ```

## MongoDB with Mongoose

-   Mongoose adalah library yang bisa dibilang sebagai Object Modelling MongoDB untuk NodeJS.

-   Mongoose bisa digunakan untuk mengelola hubungan antara data, menyediakan validasi. Dan juga digunakan untuk menerjemahkan antara objek dalam kode dan representasi Objek tersebut di MongoDB.

-   sebelum menggunakan mongoose, harus connect dulu enode js

    -   install dotenv dan mongodb

    ```
    npm install dotenv --save

    npm install mongodb --save
    ```

    -   buat satu file .env utk simpan variabel database

    ```
    MONGODB_URL=mongodb:

    MONGODB_DATABASE=namaDB
    ```

    -   membuat file utk interaksi dan koneksi DB

    ```
    require('dotenv').config

    const MongoClient = require('mongodb').MongoClient

    const url = process.env.MONGODB_URL
    const database = process.env.MONGODB_DATABASE

    MongoClient.connect(url, (err, client) => {
        if(err) throw err

        var db = client.db(database)

        db.collections('Siswa').find().toArray((err, result) => {
            if(err) throw err
            console.log(result)
            client.close()
        })

        db.collections('Siswa').insert({
            username: 'Geo',
            email: 'apaaja@gmail.com',
            country: 'indonesia'
        })
    })
    ```

    -   instalasi mongoose

    ```
    npm install mongoose
    ```

    -   create connection

    ```
    const mongoose = require('mongoose')
    require('dotenv').config()

    const url = process.env.MONGOOSE_URL

    mongoose.connect(url, {
        useNewUrlParser: true,
        useUnifiedTopology: true,
        useBindAndModify: false
    })
    const db = mongoose.connection
    db.on('error', console.error.bind(console. 'connection error'))
    db.once('open', () => console.log('we are connected'))
    ```

    -   buat file .env untuk menyimpan URL / data rahasia

    ```
    MONGOOSE_URL=mongodb://localhost:27017/dbmongoose
    ```

    -   jalankan pada terminal

    ```
    node index
    ```

# Docker intro
