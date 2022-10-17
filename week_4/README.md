# Writing Test Week 4
## **Day 1 : Javascript Intermediate (*Asynchronous-Fetch*)**
Learning Objective untuk *Asynchronous-Fetch*:
-   *Peserta mampu mengambil data API menggunakan fetch*  

    ***Fetch API*** 

    Penggunaan **Fetch API** memungkinkan aplikasi web yang dibangun untuk melakukan *HTTP request* data ke server untuk melakukan *update* konten tanpa perlu melakukan *page load*. Misal, pada aplikasi web pemesanan tiket bioskop yang perlu menampilkan film terbaru dan terpopuler pada minggu tertentu. Aplikasi web tersebut perlu melakukan **Fetch API** untuk *update* list film terbaru, tanpa harus mengubah seluruh bagian HTML. JavaScript akan melakukan proses ini lewat **DOM Manipulation APIs**, dengan data yang diminta berupa **JSON**. Misal, dengan potongan kode berikut:

        const fetchPromise = fetch('bad-scheme://mdn.github.io/learning-area/javascript/apis/fetching-data/can-store/products.json');

        fetchPromise
        .then((response) => response.json())
        .then((data) => {
            console.log(data[0].name);
        })
        .catch((error) => {
            console.error(`Could not get products: ${error}`);
        });

    Berikut adalah proses yang berjalan pada potongan kode tersebut:
    1.  `fetch()` API akan dipanggil dan mengembalikan data ke variabel **fetchPromise** 
    2.  Kemudian, data tadi akan diumpankan menuju fungsi `.then()` untuk berlanjut pada proses ***asynchronous***. Proses asinkronus ini memungkinkan **promise** memanggil respon **jika** proses *fetch* telah usai dilakukan
    3.  Nilai data yang sudah didapatkan akan diubah menjadi bentuk **json** untuk selanjutnya diumpankan menuju fungsi `.then()` selanjutnya untuk diperoleh nilai **data** yang akan ditampilkan. 
    4.  **Jika didapati proses *asynchronous* gagal**, maka akan dipanggil fungsi `catch()` dan menampilkan pesan kegagalan proses. 

-   *Peserta mampu memahami proses Asynchronous pada JavaScript* 

    ***Async Await***

    Merupakan cara mudah untuk menjalankan proses *asynchronous*. ***Async Function*** disertai dengan ***await*** di dalam fungsi untuk menunggu hingga proses *promise* berjalan hingga usai. Misal, dengan contoh potongan kode berikut:

        async function fetchProducts() {
            try {
                const response = await fetch('https://mdn.github.io/learning-area/javascript/apis/fetching-data/can-store/products.json');

                const data = await response.json();
                return data;
            }
            catch (error) {
                console.error(`Could not get products: ${error}`);
            }
        }

        const promise = fetchProducts();
        promise.then((data) => console.log(data[0].name));

    Berikut adalah proses yang berjalan pada potongan kode di atas:
    1.  Mendefinisikan fungsi `fetchProducts()` untuk menjalankan proses *asynchronous*
    2.  Dapat menggunakan blok `try...catch` untuk mengatasi error ketika proses berlangsung
    3.  Data yang didapat kemudian akan dikembalikan dalam bentuk **json**    
    4.  `catch()` akan berjalan ketika proses *asynchronous* gagal berfungsi
    5.  Nilai data yang didapatkan ketika fungsi `fetchProducts()` berlangsung akan dikembalikan dalam variabel **promise** untuk dikirim dalam fungsi `.then()` untuk menampilkan nilai data.
    
## **Day 2 : Git & GitHub Lanjutan**
Learning Objective untuk **Git & GitHub Lanjutan**:
-   *Peserta mampu berkolaborasi dengan tim menggunakan Github* 

    **Git Branch**

    Merupakan fitur yang digunakan untuk melakukan kolaborasi satu tim ketika mengembangkan suatu proyek. Git Branch mencegah terjadinya **konflik** antar-*developer* dengan memisahkan pengembangan yang dilakukan dari ***branch-master***. Untuk itu, perlu dibuat *branch* baru dengan menggunakan:

        git branch <branch>

    **Git Merge**

    Merupakan fitur yang digunakan untuk menyatukan setiap pekerjaan atau pengembangan yang telah dikerjakan oleh developer ke dalam ***branch-master***. Git Merge dapat dilakukan dengan menggunakan kode

        git checkout master

    untuk *checkout* terlebih dahulu, kemudian

        git merge <branch>

    untuk menggabungkan setiap *branch* yang ada             

## **Day 3 : Responsive Web Design & Bootstrap 5**
Learning Objective untuk **Responsive Web Design**:
-   *Peserta mampu memahami apa itu Responsive Web Design*   
    
    Adanya ***Responsive Web Design*** memungkinkan desain aplikasi website yang dirancang **dapat diakses** dengan menggunakan *device* apapun, bisa berupa PC, *mobile device*, maupun tablet. 

-   *Peserta mampu memahami dan menggunakan Media Query*

    Menggunakan **media query** memungkinkan developer merancang desain aplikasi website yang responsif terhadap semua *device* dengan menggunakan `min-width` dan `max-width`. Untuk dapat membuat **media query**, developer dapat membuat dengan menggunakan **dua** file CSS yang berbeda, atau menggabungkannya pada satu file CSS. Misal untuk dua file CSS yang berbeda, developer dapat mengatur pengaturan max-width di HTML seperti berikut:

        //Untuk tampilan pada PC 
        <link rel='stylesheet' href='styles/main.css>

        //Untuk tampilan pada mobile device dengan ukuran web < 500px
        <link rel='stylesheet' media='screen and (max-width: 500px)' href='styles/main.mobile.css>

    Atau, bisa dengan menggabungkan keduanya dalam satu file CSS, misal

        //Tampilan untuk PC
        body {
            background-color: black;
        }

        //Tampilan untuk mobile device
        @media screen and (max-width: 500px) {
            background-color: blue;
        }

-   *Peserta mampu menggunakan tools untuk membuat website yang responsif*

    Kemudian, developer dapat mengevaluasi hasil desain web responsif dengan memanfaatkan ***Chrome Dev Tools*** yang dapat diakses dengan cara `Ctrl` + `Shift` + `J` untuk sistem operasi windows. Kemudian, dapat diakses di **Toogle Device Toolbar** atau dengan *shortcut* `Ctrl` + `Shift` + `M`

Learning Objective untuk **Bootstrap 5**:
-   *Peserta mampu memahami mengapa dan kapan menggunakan Bootstrap*    

    Developer dapat menggunakan **Bootstrap** untuk membangun desain website yang responsif secara cepat lewat ketersediaan komponen dan sistem ***responsive grid frameworkd*** yang mumpuni.

-   *Peserta mampu memahami dan menggunakan layout pada Bootstrap*

    Salah satu fitur yang disediakan untuk menyediakan *layout* bagi desain yang dirancang. Salah satu elemen dasar yang ada yaitu **Containers** dengan mengakses kode berikut:

        <div class="container">
            <!-- Content here -->
        </div>

    Kemudian, ada **grid** yang memungkinkan developer mengatur dimensi dari *layout* yang dirancang dengan kode berikut:
        
        <div class="container">
            <div class="row">
                <div class="col-sm">
                    One of three columns
                </div>
                <div class="col-sm">
                    One of three columns
                </div>
                <div class="col-sm">
                    One of three columns
                </div>
            </div>
        </div>

    yang memungkinkan pengaturan dimensi kolom pada setiap barisnya.  

-   *Peserta mampu memahami dan mengunakan component pada Bootstrap*    

    Bootstrap juga menyediakan **komponen** yang sangatlah banyak jumlahnya. Komponen-komponen ini dapat diakses dengan menambahkan **kelas** dari setiap komponen pada *nested* `<span>`. Misal, 

        <button type="button" class="btn btn-default" aria-label="Left Align">
            <span class="glyphicon glyphicon-align-left" aria-hidden="true"></span>
        </button>