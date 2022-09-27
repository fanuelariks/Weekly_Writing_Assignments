# Writing Test Week 1
## **Day 1 : Unix Command Line, serta Git & GitHub Dasar**
Learning Objective untuk Command Line:
- *Peserta mampu menggunakan command untuk melihat isi files*  

    Untuk dapat melihat isi file yang ada pada direktori, programmer dapat menggunakan kode **cat** untuk melihat isi keseluruhan dari file tersebut. Jika hanya ingin melihat isi file di bagian awal saja, maka programmer dapat menggunakan kode **head** yang akan menampilkan beberapa line awal, sedangkan jika sebaliknya, programmer dapat menggunakan kode **tail** yang akan menampilkan beberapa line akhir dari isi file tersebut

- *Peserta mampu menggunakan command untuk memindahkan atau me-rename file dan direktori*

    Untuk dapat memindahkan file maupun direktori, programmer dapat menggunakan kode **mv** yang mana lewat kode tersebut, programmer juga dapat mengganti nama file maupun direktori ke nama baru yang diinginkan

-  *Peserta mampu menggunakan command untuk melihat current working directory*

    Untuk dapat melihat *current working directory*, programmer dapat memasukkan kode **pwd** atau *Print Working Directory* dimana akan menampilkan posisi programmer pada direktori mana saat itu

- *Peserta mampu menggunakan command untuk melihat isi sebuah directory*

    Untuk dapat melihat isi sebuah direktori, programmer dapat menggunakan kode **ls** atau *lists* yang akan menampilkan isi file yang ada pada direktori yang programmer tuju

- *Peserta mampu menggunakan command untuk membuat file & direktori*

    Untuk dapat membuat file baru, programmer dapat menggunakan kode **touch**, sedangkan untuk membuat direktori baru, programmer dapat menggunakan kode **mkdir** untuk kemudian menginput nama file/direktori yang diinginkan

Learning Objective untuk Git & GitHub Dasar:
- *Peserta mampu memahami perbedaan antara Git dan Github*   

    Secara sederhana, Git merupakan sistem kontrol yang dapat digunakan oleh programmer untuk manajemen proyek serta menelusuri rekam jejak kode yang dibangun, sedangkan GitHub merupakan fasilitas penyimpanan *cloud* yang dapat digunakan oleh programer untuk manajemen repositori proyek dan membuka kolaborasi antar-programmer

-   *Peserta mampu memahami dan membuat Repository Git*

    Untuk dapat membuat repositori, saya melampirkan penjelasan dari [GitHub Docs](https://docs.github.com/en/get-started/quickstart/create-a-repo) seperti berikut:
    
    1. Pada sisi kanan layar, programmer dapat memilih ikon **+** dan memilih ***New Repository***
    2. Ketikkan nama repositori yang diinginkan serta bisa juga ditambahkan deskripsi mengenai repositori tersebut
    3. Kemudian, programmer dapat memilih sifat dari repositori tersebut, apakah bersifat *public*, *internal*, maupun *private*
    4. Kemudian, progammer memilih untuk menginisasi repository tersebut dengan **README**
    5. Terakhir, programmer dapat menyelesaikan pembuatan repositori dengan memilih ***Create Repository***

-   *Peserta mampu melakukan cloning Github ke local*

    Repositori pada GitHub bersifat *remote* yang mana memungkinkan programmer untuk bekerja secara independen tanpa memengaruhi file utama yang ada pada repositori dengan cara **kloning** file tersebut ke repositori lokal pada komputer. Berikut adalah cara untuk kloning file yang saya sadur dari [GitHub Docs](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/adding-and-cloning-repositories/cloning-and-forking-repositories-from-github-desktop)
    
    1. Pada bagian menu di file, programmer dapat memilih ***Clone Repository***
    2. Programmer dapat memilih repositori mana yang akan dikloning dengan memilih langsung atau memasukkan link URL
    3. Kemudian, programmer memilih repositori lokal pada komputer 
    4. Programmer dapat memilih ***Clone***

## **Day 2 : *Hyper Text Markup Language* (HTML)**
Learning Objective untuk HTML:
-   *Peserta mampu membuat HTML sederhana*
    
    Berikut adalah salah satu contoh HTML sederhana yang saya buat:
    ><head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Practice</title>
        <link rel = 'stylesheet' href = 'style.css' />
    </head>

-   *Peserta mampu memahami dan mengimplementasikan tag HTML yang populer*
    
    Berikut adalah salah satu contoh implementasi tag HTML yang populer, yaitu **img** seperti berikut:

        <img src="image-removebg-preview.png" class="logo" alt="">

    Lewat penggunaan kode di atas, saya dapat menampilkan suatu objek gambar yang saya ambil dari sumber terkait lewat link yang saya cantumkan
-   *Peserta mampu memahami dan mengimplementasikan semantic HTML*

     Elemen semantik merupakan elemen pada HTML yang dapat mendeskripsikan elemen tersebut baik untuk browser yang digunakan maupun programmer yang menyusun elemen tersebut. Salah satu contoh elemen semantik yang saya bangun seperti berikut:

        <section id="hero">
        <h1>2022 Belgian GP</h1>
        <h3>Akkodis F1 Race Debrief</h3>
        <button>Read Now</button>
        </section>

-   *Peserta dapat mempublish website sampai ke tahap deployment*

    Untuk sampai ke tahap *deployment*, programmer dapat memanfaatkan *tools* yaitu ***Netlify*** dengan langkah seperti berikut:

    1. Setelah masuk ke **Netlify**, programmer perlu menghubungkan *Add A New Project* yang sudah dipilih ke repository file di GitHub
    2. Programmer perlu untuk mengizinkan akses dari **Netlify** ke GitHub
    3. Setelah selesai, programmer memilih repo mana yang akan dihubungkan untuk membangun website
    4. Kemudian, programmer perlu mengatur penyesuaian agar website yang di-*publish* sesuai dengan ketentuan 
    5. Selesai 

## **Day 3 : *Cascading Style Sheets* (CSS)**
Learning Objectives untuk CSS:

-   *Peserta mampu memahami beberapa cara menyisipkan CSS ke dalam HTML*

    Ada beberapa cara untuk menyisipkan CSS ke dalam HTML, berikut adalah penejelasannya:

    1. *Inline Styles*

        Inline styles akan menambahkan CSS pada *attribute* HTML seperti berikut:

            <p style="color: magenta; font-size: 36px;">Halo ini contoh</p>
        <p style="color: magenta; font-size: 36px;">Halo ini contoh</p>

    2. *Internal Style*

        Internal style akan menambahkan CSS pada *attribute* HTML dengan kode < style >. Berikut adalah contohnya:

            <style>
                h1 {
                    color: yellow;
                }
            </style>
            <body>
                <h1>Apa kabar?</h1>
            </body>            
        <style>
            h1 {
                color: yellow;
            }
        </style>
        <body>
            <h1>Apa kabar?</h1>
        </body>

    3. *External Style*

        External style akan menambahkan CSS pada HTML dengan menghubungkan file CSS lewat kode < link >                    

-   *Peserta mampu memahami dan menggunakan sintaks dasar dari CSS*

    Sintaks CSS digunakan untuk memilih elemen HTML mana yang akan diberi *style*. Sintaks ini terdiri atas ***selector, value,*** dan ***property***. Berikut adalah susunan sintaksnya:

        selector {
            property: value;
        }
    Berikut adalah penejelasan singkatnya:

    - **Selector** merupakan elemen HTML yang dipilih untuk diedit
    - **Properti** merupakan bagian dari *selector* yang akan diedit, misal warna
    - **Value** merupakan nilai properti yang akan diterapkan, misal warna merah

-   *Peserta mampu memahami dan menggunakan flexbox*

    Pengertian dari *flexbox* merupakan cara yang dapat digunakan untuk mengatur layout dari website yang dibangun secara fleksibel. Dua elemen penting dari *flexbox* yaitu ***container*** dan ***item***. 

        <style>
		    #flex-container {
			    display: flex;
			    flex-direction:row;
		    }
		    .flex-item {
                flex-basis: 100%;
                height: 100px;
                margin: 4px;
                background: #ec5453;
                font-size: 60px;
                color: white;
                text-align: center;
            }
	    </style>   

    Selain dengan menggunakan ***flex-direction:row***, bisa juga menggunakan ***justify-conten*** dengan properti seperti berikut:

    - ***flex-start*** di mana semua konten akan ditampilkan di awal layout
    - ***flex-end*** di mana semua konten yang diatur akan ditampilkan di akhir layout
    - ***center*** di mana semua konten akan ditampilkan di tengah layout
    - ***space-between*** di mana pengaturan ini akan memberi ruang pada setiap konten yang bersebelahan
    - ***space-around*** di mana pengaturan ini akan memberi ruang di sekeliling tiap konten yang diatur

## **Day 4 : Algoritma dan Javascript Awal**
Learning Objectives untuk Algoritma:

-   *Peserta mampu memahami perbedaan antara Algoritma dan Data Structures*

    Secara umum, **Algoritma** merupakan langkah logis yang digunakan untuk menyelesaikan suatu masalah. Algoritma akan menyelesaikan masalah tersebut menggunakan data yang dikelola atau dimanajemen oleh **Data Struktur**.

-   *Peserta mampu membuat algoritma sederhana*

    Algoritma dapat disusun secara **deskriptif, diagram alir,** maupun ***pseudo-code***. Berikut adalah salah satu contoh algoritma secara diagram alir:

    ![Diagram Alir](https://www.researchgate.net/profile/Bayu-Prianto/publication/304112039/figure/fig1/AS:669451615735823@1536621111683/Gambar-2-1-Diagram-alir-penentuan-struktur-keadaan-dasar-Sumber-Prianto-2005.jpg)


-   *Peserta mampu memahami dan menerapkan salah satu algoritma dengan JavaScript*

    Berikut adalah contoh penerapan algoritma dengan Javascript secara ***pseudo-code***:

    **Tukar isi antara 2 wadah berikut:**

        let A = "Kopi"
        let B = "Teh"
        let C = ""

        C = A
        A = B
        B = C

        console.log(A,B)

-   *Peserta mampu memahami dan menerapkan salah satu struktur data dengan JavaScript*

    Berikut adalah contoh penerapan struktur data pada Javascript:

        const arr = ['bison', 'ant', 'camel']
        console.log(arr.indexOf('ant'));
        //expected output: 1

Learning Objectives untuk Javascript:

-   *Peserta mampu memahami dan membedakan berbagai tipe data*

    Untuk tipe data pada Javascript dapat dibedakan menjadi:

    - **Number**, misal 

            let number = 17;

    - **String**, misal

            let nama = 'fanuel';

    - **Boolean**, misal

            let var1 = true;
            let var2 = false;

    - **Null**, misal

            let A = null;
            //expected output: null

    - **Undefined**, misal

            let var1 = "apa";
            console.log(var2);
            //expected output: undefined  

    - **Object**, misal

            var siswa {
                orang = 'fanuel',
                usia  = 17,
                suku  = 'batak',
            }              

-   *Peserta mampu memahami dan menggunakan operator*

    Javascript memiliki beberapa operator yang terdiri atas:

    - **Assignment Operator (=)** dengan tujuan untuk menyimpan value pada variabel tertentu. Misal, 

            let var1 = "apa";

    - **Arithmetic Operator** dengan tujuan untuk operasi matematis. Misal, 

            console.log(11 % 3);
            //expected output: 2        

    - **Comparison Operator** dengan tujuan untuk membandingkan dua data. Misal,

            let var1 = "apa";
            let var2 = "tidak";
            console.log(var1===var2);
            //expected output: 'false'

## **Day 5 : Javascript Awal (*Conditional* dan *Looping*)**      

-   *Peserta mampu memahami dan membedakan control flow (conditional dan looping)*

    Secara umum, pengertian dari ***conditional*** adalah sebuah *statement* percabangan yang menggambarkan suatu skenario atau kondisi. *Conditional* akan menjalankan instruksi berdasarkan kondisi yang ada dan mengeluarkan nilai **true** jika kondisi sesuai dan **false** jika sebaliknya

    Berikut adalah beberapa *conditional statement* yang sering digunakan:

    1. ***IF Statement*** misal, **"jika aku lapar, aku makan"** dengan struktur berikut:

            let lapar == true;
            if (lapar) {
                console.log("Aku akan makan");
            }

    2. ***IF.. Else Statement*** misal, **"jika lapar, aku makan, jika tidak, aku tidak makan** dengan struktur berikut:

            let lapar == true;
            if (lapar) {
                console.log("Aku akan makan");
            } else {
                console.log("Aku tidak makan");
            }  

    3. ***Switch Case Conditional*** dapat digunakan jika kondisi percabangan yang terlalu banyak, misal:

            switch(expression)  {
                case value_1:
                    statement_1;
                    break;
                case value_2:
                    statement_2;
                    break;
                default:
                    default_statement;        
            }
            
    4. ***Ternary Operator*** dapat digunakan sebagai metode singkat dari *if.. else conditional*. Berikut adalah contohnya

             let lapar = true;
             lapar ? console.log("Aku mau makan") :         
             console.log("Aku tidak mau makan");

    Untuk ***looping*** merupakan *statement* yang mengulang instruksi hingga suatu kondisi yang diminta terpenuhi. Berikut adalah *looping* yangn sering digunakan

    1. ***For Loop*** dapat digunakan untuk pengulangan jika kita mengetahui jumlah iterasi yang akan diterapkan, misal

            let angka = 10;
            for (angka; angka>0; angka--) {
                console.log(angka);
            }             

    2. ***While Loop*** dapat digunakan untuk pengulangan pada kondisi **true** dan jika programmer tidak mengetahui jumlah iterasi yang diterapkan, misal

            let jumlah = 1;
            while (jumlah <= 10) {
                console.log(count);
                count += 2;
            }

    3. ***Nested Loop*** merupakan pengulangan di dalam pengulangan. Berikut adalah contohnya

            int weeks = 2;
            int days  = 7;

            for (int i = 1; i <= weeks; ++i){
                console.log("Minggu ke-" + i);

                for (int j = 1; j <= days; ++j){
                    console.log("Hari ke-" + j);
                }
            } 
