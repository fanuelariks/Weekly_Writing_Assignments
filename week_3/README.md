# Writing Test Week 3
## **Day 1 : Javascript Intermediate (*Array and Multidimentional Array*)**
Learning Objective untuk *Array and Multidimentional Array*:
-   *Peserta mampu memahami dan menggunakan struktur data Array*  

1.  ***Array*** 

    Secara umum, fungsi dari **array** adalah untuk **mengorganisasi dan menyimpan** berbagai tipe data dalam bentuk list order. Berikut adalah contoh sederhananya:

        let dataSsiwa = {
            "Fanuel",
            21,
            "Yogyakarta"
        };

    -   **Mengakses Array**

        Untuk dapat mengakses array yang ada, dapat digunakan metode berikut:

            let dataSsiwa = {
                "Fanuel",
                21,
                "Yogyakarta"
            };   
            //Menampilkan data array nama Fanuel
            console.log(dataSiswa[0])

        Pada JavaScript, data pada array **pertama** terhitung menjadi **data ke-0**. Itulah mengapa untuk mendapatkan nama ```Fanuel```, dipanggil array ```dataSiswa``` pada index ke-0.    

    -   **Update Data Array**   

        Untuk dapat mengedit data pada array, dapat dilakukan dengan metode berikut:

            let dataSsiwa = {
                "Fanuel",
                21,
                "Yogyakarta"
            };   

            //Mengedit data siswa dari Yogyakarta menjadi Purworejo
            dataSiswa[2] = "Purworejo";
            console.log(dataSiswa);

    -   **Array Properties**

        Salah satu properti pada array yang sering digunakan adalah ```.length``` yang dapat mengembalikan nilai panjang suatu array, dihitung lewat jumlah index yang ada. Misal, 

            let dataSsiwa = {
                "Fanuel",
                21,
                "Yogyakarta"
            }; 

            //Untuk menampilkan panjang suatu array
            console.log(dataSiswa.length);   

    -   **Array Method**

        *Method* merupakan fasilitas yang disediakan oleh JavaScript untuk memudahkan programmer dengan menyediakan **fungsi *built-in***. Berikut adalah beberapa contoh metode array.

        -   **.push()** digunakan untuk menambahkan item ke dalam array. Contoh:  

                let dataSiswa = {
                    "Fanuel",
                    21,
                    "Yogyakarta" 
                }            

                //Menggunakan .push()
                dataSiswa.push("Belum Menikah");
                console.log(dataSiswa);

        -   **.pop()** digunakan untuk menghapus item dalam array dengan index terakhir. Contoh:

                let dataSiswa = {
                    "Fanuel",
                    21,
                    "Yogyakarta"
                    "Belum Menikah"
                } 

                //Menggunakan .pop()
                dataSiswa.pop();
                console.log(dataSiswa);

                //Output = {"Fanuel", 21, "Yogyakarta"};


        -   **.shift()** digunakan untuk menghapus item dalam array dengan index pertama. Contoh:

                let dataSiswa = {
                    "Fanuel",
                    21,
                    "Yogyakarta"
                } 

                //Menggunakan .shift()
                dataSiswa.shift();
                console.log(dataSiswa);

                //Output = {21, "Yogyakarta"};

        -   **.unshift()** digunakan untuk menambahkan item dalam array dengan index pertama. Contoh:

                let dataSiswa = {
                    21,
                    "Yogyakarta"
                } 

                //Menggunakan .unshift()
                dataSiswa.unshift("Fanuel");
                console.log(dataSiswa);

                //Output = {"Fanuel", 21, "Yogyakarta"};

        -   **.slice()** digunakan untuk mengambil data dari sebuah array dan mengembalikannya menjadi sebuah array tersendiri. Contoh:


                let dataSiswa = {
                    "Fanuel"
                    21,
                    "Yogyakarta"
                } 

                //Menggunakan .slice(batasAwal, batasAkhir)
                
                let usiaKota = dataSiswa.slice(-2)
                console.log(usiaKota);

                //Output = {21, "Yogyakarta"};    

        -   **.splice()** dapat digunakan untuk **menghapus** data yang ada dalam array maupun **menambahkan** atau menggantikan data yang dihapus tadi. Contoh:
        
                let dataSiswa = {
                    "Fanuel"
                    21,
                    "Yogyakarta"
                } 

                //Menggunakan .splice(batas, berapa,"data1","data-n")
                
                dataSiswa.splice(1, 0, "Mahasiswa", "Lajang")
                console.log(dataSiswa);

                //Output = {"Fanuel", 21, "Mahasiswa", "Lajang" "Yogyakarta"};                         
    -   **Looping** 

        Array juga memiliki *built-in methods* untuk dapat melakukan looping, yaitu **.map()** serta **.forEach()**. Berikut adalah penjelasannya. 

        -   **.map(currentValue, Index)** merupakan metode yang dapat melakukan looping dan **mengembalikannya** dalam bentuk array baru. Contoh:

                let arr =  [1,2,3,4];

                const returnValue = array.map((num) => {
                    return num * 10;
                })

                console.log(returnValue);

                //Output
                [10,20,30,40]
                0:10
                1:20
                2:30
                3:40
                length: 4

        -   **.forEach(currentValue, Index)** merupakan metode yang dapat melakukan looping, namun **tidak dapat mengembalikannya** dalam bentuk array baru. Contoh:

                let arr =  [1,2,3,4];

                const returnValue = array.forEach((num) => {
                    return num * 10;
                })

                console.log(returnValue);

                //Output
                undefined

            Berikut adalah contoh yang **tidak dikembalikan** dalam bentuk array:

                let arr =  [1,2,3,4];

                const returnValue = array.forEach((num,index) => {
                    arr[index] = num * 10;
                })

                console.log(returnValue);

                //Output
                10,20,30,40    

2.  ***Multidimentional-Array*** 

    Secara umum, **multidimensional-array** merupakan ***array di dalam array***. Analogi mudahnya adalah seperti sebuah tabel yang terdiri atas baris (setiap *array*) dan kolom (index dari setiap *array*). Misal, 

        let inventoryBaju = [
            ['kaos kerah', 10],
            ['shirt', 15],
            ['topi', 30],
            ['jaket jeans', 6],
        ];
        console.log(inventoryBaju);

    **Multidimensonal-array** dapat menggunakan properti dan metode *built-in* yang **sama seperti array**. Misal,

        //Mengakses index dalam array
        let inventoryBaju = [
            ['kaos kerah', 10],
            ['shirt', 15],
            ['topi', 30],
            ['jaket jeans', 6],
        ];
        console.log(inventoryBaju[2][1]);

        //Output
        30

    Kemudian, contoh lain penggunaan metode ```.push()``` seperti berikut:

        let inventoryBaju = [
            ['kaos kerah', 10],
            ['shirt', 15],
            ['topi', 30],
            ['jaket jeans', 6],
        ];

        //Menambahkan array ke dalam array
        inventoryBaju.push(['celana jeans', 7]);

        console.log(inventoryBaju);    

        //Output
        [
            ['kaos kerah', 10],
            ['shirt', 15],
            ['topi', 30],
            ['jaket jeans', 6],
            ['celana jeans', 7]
        ]

    Selanjutnya, **multidimensional-array** juga dapat di-*looping* dengan menggunakan ```.map()``` maupun ```.forEach()```. Misal, 

        let inventoryBaju = [
            ['kaos kerah', 10],
            ['shirt', 15],
            ['topi', 30],
            ['jaket jeans', 6],
        ];    

        //Menggunakan .map() untuk menghitung produk yang terjual dengan asumsi jumlah awal adalah 150 stok

        inventoryBaju.map(dataBaju => {
            let dataJual = 150 - dataBaju[1];
            dataBaju[2] = dataJual;
        })

        console.table(dataBaju);

    Atau, bisa juga untuk menggunakan ```.forEach()``` seperti berikut:

        let inventoryBaju = [
            ['kaos kerah', 10],
            ['shirt', 15],
            ['topi', 30],
            ['jaket jeans', 6],
        ];  

        //Menggunakan .forEach() 

        inventoryBaju.forEach()

## **Day 2 : Javascript Intermediate (*Object*)**
Learning Objective untuk *Object*:  

-   *Peserta mampu memahami dan menggunakan struktur data Object*

    Contoh penggunaan objek layaknya sebuah *array* yang dapat menyimpan properti dengan tipe data apapun. 

        let person {
            nama: 'Fanuel Ari',
            umur: 21,
            domisili: 'Yogyakarta',
        }
        console.log(person);

    Programmer juga mampu mengupdate data pada objek dengan menggunakan struktur berikut:

        let person {
            nama: 'Fanuel Ari',
            umur: 21,
            domisili: 'Yogyakarta',
        }

        //Menambahkan properti objek baru
        person.umur = 25;
        person.pekerjaan = 'Mahasiswa';

        console.log(person);

        //Output
        {
            nama: 'Fanuel Ari',
            umur: 25,
            domisili: 'Yogyakarta',
            pekerjaan:'Mahasiswa',
        }

        //Menghapus properti objek
        delete person.domisili;
        
        console.log(person);

        //Output
        {
            nama: 'Fanuel Ari',
            umur: 25,
            pekerjaan:'Mahasiswa',
        }

    Kemudian, programmer juga dapat membuat sebuah *method* secara kustom sesuai dengan kebutuhan kita. Misal, 

        const sapa = {
            menu: function() {
                return 'Silakan pilih menu yang diinginkan';
            }, 
            pembayaran: function() {
                return 'Silakan menuju ke kasir';
            },
        };

        console.log(sapa.menu()); 
        //Output 'Silakan pilih menu yang diinginkan'

    Selain itu, dikenal juga **nested object** seperti contoh berikut

        const teams = {
            head: 'Toto Wolff',
            technician: 'James Allison',
            driver: {
                name: 'Lewis Hamilton',
                age: 37
                country: 'Great Britain',
            }
        };    

        console.log('His name is', teams.head);
        //Output 'His name is Toto Wolff'

    Selain itu, pada objek juga dimungkinkan untuk melakukan *looping* untuk menampilkan seluruh data. Contoh

        const teams = {
            head: 'Toto Wolff',
            technician: 'James Allison',
            driver: {
                name: 'Lewis Hamilton',
                age: 37
                country: 'Great Britain',
            }
        };

        //Penggunaan for untuk looping
        for(let data in teams.driver) {
            console.log(teams.driver[data]);
        }

        // 'Lewis Hamilton'
        // 37
        // 'Great Britain'

-   *Peserta mampu memahami dan menggunakan struktur data Array of Objects*

    Penggunaan *array of objcect* memungkinkan objek untuk menyimpan banyak data. Misal, 

        let champions = [
        {    
            name: 'Lewis Hamilton',
            age: 37,
            country: 'Great Britain',
        },
        {
            name: 'Max Verstappen',
            age: 25,
            country: 'Netherlands',
        },
        {
            name: 'Sebastian Vettel'
            age: 35,
            country: 'Germany'
        }
        ];

        champions.forEach((championsClub) => {
            console.log(championsClub);
        });

## **Day 3 : Javascript Intermediate (*Recursive*)**
Learning Objective untuk *Recursive*:  

-   *Peserta mampu memahami dan membuat program Rekursif* 

    ***Recursive*** merupakan fungsi yang memanggil dirinya sendiri sampai pada kondisi tertentu. Misal, 

        function countDown(number) {
            console.log(number);

            const newNumber = number - 1;
            if (newNumber > 0) {
                countDown(newNumber);
            }
        }

        countDown(4);
        //Output
        4
        3
        2
        1

## **Day 4 : Javascript Intermediate (*Asynchronous*)**
Learning Objective untuk *Asynchronous*:  

-   *Basic Asynchronous of JavaScript*       
    
    Secara umum, *asynchronous* merupakan teknik yang dapat menjalankan suatu program untuk mengerjakan suatu *task* lain **sembari menunggu** proses yang masih berlangsung. Padahal, JavaScript merupakan bahasa pemrograman ***single-thread*** yang hanya mampu menjalankan satu task saja atau disebut ***synchronous***. Untuk itu, ada tiga cara untuk membuat *asynchronous* secara simulasi, yaitu:

    -   **Callback** merupakan fungsi yang ada di dalam argumen/parameter pada sebuah fungsi, di mana fungsi tersebut akan dieksekusi setelah fungsi pertama menjalankan tugasnya. Misal, 

            console.log('fired first');
            console.log('fired second');

            setTimeout(() => {
                console.log('fire third');
            }, 2000);

            console.log('fired last');

            //Output
            fired first
            fired second
            fired last
            fired third

    -   **Promise** merupakan fitur yang disediakan oleh JavaScript untuk melakukan HTTP request atau *fetch* data dari API. Misal, 

            const getData = () => {
                return new Promise ((resolve, reject) => {
                    let condition = true;
                    if (condition) {
                        resolve('requested')
                    } else {
                        reject(new Eror('request failed'))
                    }
                }).then(result => {console.log(result)})
                  .catch(error => {console.log(error)})
            }          
            getData()

## **Day 5 : Javascript Intermediate (*Web-Storage*)**
Learning Objective untuk *Web-Storage*:  

-   *Peserta mampu memahami dan memanipulasi data menggunakan Web Storage*       
    
    ***Web-storage*** memungkinkan programmer untuk menyimpan data secara *local* untuk aplikasi web yang dibangun. *Web-storage* tersedia per domain dan protokol sehingga memungkinkan setiap halaman untuk menyimpan data. Terdapat dua objek data storing, yaitu:

    -   ***The localStorage Object*** memungkinkan programmer menyimpan data **tanpa** batas waktu dan data yang disimpan **tidak akan dihapus** ketika kita menutup *browser*. Misal,

            function clickCounter() {
                if (typeof(Storage) !== "undefined") {
                    if(localStorage.clickcount) {
                        localStorage.clickcount = Number(localStorage.clickcount) +1'
                    } else {
                        localStorage.clickcount = 1;
                    }
                    document.getElementById("result").innerHTML = "Anda sudah menekan klik sebanyak " + localStorage.clickcount + " kali.";
                } else {
                    document.getElementById("result").innerHTML = "Maaf, browser anda tidak mendukung web storage";
                }
            }

    -   ***The sessionStorage Object*** memungkinkan programmer menyimpan data, namun hanya pada **sesi tertentu** sehingga data akan dihapus ketika browser ditutup. Misal,

            function clickCounter() {
                if (typeof(Storage) !== "undefined") {
                    if(sessionStorage.clickcount) {
                        sessionStorage.clickcount = Number(sessionStorage.clickcount) +1'
                    } else {
                        sessionStorage.clickcount = 1;
                    }
                    document.getElementById("result").innerHTML = "Anda sudah menekan klik sebanyak " + sessionStorage.clickcount + " kali.";
                } else {
                    document.getElementById("result").innerHTML = "Maaf, browser anda tidak mendukung web storage";
                }
            }
