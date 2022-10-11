## Javascript Array

-   Array adalah tipe data list order yang dapat menyimpan tipe data apapun di dalamnya. Array dapat menyimpan tipe data String, Number, Boolean, dan lainnya.

-   syntax array

    ```
    let animals = ['dog', 'cow', 'chicken']

    let animals = [
        'dog',
        'cow',
        'chicken'
    ]
    ```

-   array dapat diakses melalui index, array pada JS merupakan zero indexing (index yg dimulai dari nol)

-   cara mengakses nilai array

    ```
    let plants = ['grass', 'coconut', 'wheat']

    console.log(plants[0]) // output = 'grass'
    console.log(plants[1]) // output = 'coconut'
    console.log(plants[2]) // output = 'wheat'
    ```

-   mengupdate nilai pada array

    ```
    const urutan = [1, 2, 4, 3]

    urutan[2] = 3
    urutan[3] = 4

    console.log(urutan) // output = [1, 2, 3, 4]
    ```

-   pada contoh diatas, array dideklarasikan sebagai const, tetapi nilai dari elemennya masih dapat diubah, selama tidak menginisialisasikan keseluruhan nilai array

-   array memiliki 5 property yg sering digunakan

    -   constructor
    -   length
    -   index
    -   input
    -   prototype

-   property merupakan fitur yang sudah disediakan oleh Javascript untuk memudahkan developer.

-   methods pada array

    -   .push(), berfungsi untuk memasukkan nilai ke akhir array

        ```
        const ancientWeapon = ['pluton', 'poseidon']

        ancientWeapon.push('uranus')

        console.log(ancientWeapon) // output = ['pluton', 'poseidon', 'uranus']
        ```

    -   .pop(), digunakan untuk menghapus item array index terakhir

        ```
        const trioAdmiral = ['akainu', 'aokiji', 'kizaru', 'kaido']

        trioAdmiral.pop()

        console.log(trioAdmiral) // output = ['akainu', 'aokiji', 'kizaru']
        ```

    -   .shift(), digunakan untuk menghapus item array pada index paling awal

        ```
        let yonkou = ['sakazuki', 'shanks', 'kaido', 'big mom', 'kurohige']

        yonkou.shift()

        console.log(yonkou) // output = ['shanks', 'kaido', 'big mom', 'kurohige']
        ```

    -   .unshift(), digunakan untuk menambahkan item array pada index paling awal

        ```
        let germa66 = ['ichiji', 'niji', 'sanji', 'yonji']

        germa66.unshift('reiju')

        console.log(germa66) // output = ['reiju', 'ichiji', 'niji', 'sanji', 'yonji']
        ```

    -   .sort(), digunakan untuk mengurutkan array secara ascending

        ```
        const numbers = [1, 5, 2, 4, 3]

        numbers.sort()

        console.log(numbers) // output = [1, 2, 3, 4, 5]
        ```

-   array looping built-in methods

    -   .map(), looping yg digunakan untuk membuat array baru

        ```
        let joestar = ['jonathan', 'joseph', 'jotaro', 'josuke', 'jolyne']

        let joestarFullName = joestar.map(e => {
            return e + ' joestar'
        })

        console.log(joestarFullName)

        // output = [
            'jonathan joestar',
            'joseph joestar',
            'jotaro joestar',
            'josuke joestar',
            'jolyne joestar'
        ]
        ```

    -   .forEach(), method untuk melakukan looping pada setiap elemen array

        ````
        const pillarMen = ['ACDC', 'Wamuu', 'Kars']

        pillarMen.forEach(e => {
            console.log(`${e) killed by Joseph Joestar`)
        })        ```
        ````

## Multidimensional Array

-   bisa dikatakan sebagai array dalam array

    ```
    let inventory = [
        ['kaos polos', 2],
        ['jaket hoodie', 5],
        ['topi', 6],
        ['celana jeans', 9]
    ]
    ```

-   mengakses multidimensional array

    ```
    let inventory = [
        ['kaos polos', 2],
        ['jaket hoodie', 5],
        ['topi', 6],
        ['celana jeans', 9]
    ]

    console.log(inventory[1][0]) // output = 'jaket hoodie'
    ```

-   methods dan fungsi pada array juga berlaku pada multidimensional array

## Javascript Object

-   object adalah sebuah tipe data pada variabel yang menyimpan properti dan fungsi (method)

-   Properti adalah data lengkap dari sebuah object.

-   Method adalah action dari sebuah object. Apa saja yang dapat dilakukan dari suatu object.

-   membuat object

    ```
    let person = {
        name: 'john cena',
        age: 43,
        isVerified: true,
    }

    let person = {
        name: 'john cena'
        age: 43,
        'is verified': true, // apabila menggunakan spasi pada key, tutup dengan ''
    }
    ```

-   mengakses object

    ```
    let person = {
        name: 'john cena',
        age: 43,
        isVerified: true,
    }

    console.log(person.name) // output = 'john cena'
    console.log(person.age) // output = 43
    console.log(person.isVerified) // output = true
    ```

-   mengupdate object

    -   object dapat mengupdate value dari key yang telah tersedia

        ```
        let person = {
            name: 'john cena',
            age: 43,
            isVerified: true,
        }

        person.name = 'joko subianto'
        ```

    -   object dapat menambahkan key dan value baru

        ```
        let person = {
            name: 'john cena',
            age: 43,
            isVerified: true,
        }

        person.isProgrammer = false
        ```

-   menghapus object property

    ```
    let person = {
        name: 'john cena',
        age: 43,
        isVerified: true,
    }

    delete people.age
    ```

-   object looping
    ```
    for(let key in object) {
        // do something to each key / value
    }
    ```
-   array of object, biasanya digunakan sebagai bentuk data dalam API
    ```
    let arr = [
        {
            nama: 'perempuan tanah jahannam'
            author: 'joko anwar'
        },
        {
            nama: 'sebelum iblis menjemput'
            author: 'joko anwar'
        },
        {
            nama: 'pintu terlarang',
            author: 'joko anwar'
        },
    ]
    ```

## Javascript Rekursif

-   Recursive adalah function yang memanggil dirinya sendiri sampai kondisi tertentu.

-   Recursive kebanyakan digunakan untuk case matematika, fisika, kimia dan yang berhubungan dengan calculation.

    ```
    function recursive() {
        // some code

        recursive()

        // some code
    }
    ```

-   ciri rekursif

    -   Fungsi rekursif selalu memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti. Kondisi ini harus dapat dibuktikan akan tercapai, karena jika tidak tercapai maka kita tidak dapat membuktikan bahwa fungsi akan berhenti, yang berarti algoritma kita tidak benar.
    -   Fungsi rekursif selalu memanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya. Hal ini penting diingat, karena tujuan utama dari rekursif ialah memecahkan masalah dengan mengurangi masalah tersebut menjadi masalah-masalah kecil.

-   contoh kasus rekursif

    ```
    function countDown(fromNumber) {
        console.log(fromNumber)

        let nextNumber = fromNumber - 1

        if(nextNumber > 0) {
            countDown(nextNumber)
        }
    }

    countDown(3)

    // output
    //1
    //2
    //3
    ```

## Javascript Asynchronous

-   fungsi dari asynchronous pada JS adalah untuk multitasking melaksanakan tugas lain selagi tugas utama masih menunggu diselesaikan oleh thread lainnya
-   asynchronous dilakukan ketika sebuah task dirasa memerlukan waktu yang lama untuk diproses, sehingga dengan melakukan multitasking, bisa mengerjakan yang lain dulu sembari meunggu main thread menyelesaikan tugasnya
-   synchronous programming adalah program yang bersifat blocking, artinya ia tidakbisa mengerjakan yugas selanjutnya apabila tugas sebelumnya belum terselesaikan
-   syntax untukmendefinisikan asynchronous javascript
    -   setTimeout
    -   async await
    -   promise
    -   callback
