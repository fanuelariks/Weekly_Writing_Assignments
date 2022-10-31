# Writing Test Week 5
## **Day 1 : Web Server & RESTful API**
Learning Objective untuk *Web Server & RESTful API*:
-   *Peserta mampu memahami konsep dari web server*  

    - Secara umum, web server terdiri atas dua bagian penting, yaitu *Hardware* dan *Software*.
    
        ***Hardware*** 

        Bagian **perangkat keras** merupakan komputer yang **menyimpan** perangkat lunak dari web server dan juga file-file lain yang mendukung, misal HTML, CSS, maupun JavaScript. Perangkat keras inilah yang memungkinkan untuk terhubung dengan internet.

        ***Software***

        Bagian **perangkat lunak** merupakan bagian yang memungkinkan **web untuk mengakses *hosted file.*** Biasanya, perangkat lunak ini berbentuk **HTTP server** yang dapat diakses melalui **domain** website dalam bentuk **HTTP Request** dan mengirim konten dari pihak server dalam bentuk **HTTP Response.**

    - Akses web server ini juga terdiri atas dua bagian, yaitu:

        ***Static Web Server*** 

        Web server ini merupakan skema sederhana di mana hanya terdiri atas **perangkat keras** dan **perangkat lunak** berupa **HTTP Server** yang mengirim *hosted files* menuju browser

        ***Dynamic Web Server***

        Web server ini merupakan skema yang lebih dinamis dengan menggabungkan ***static web server*** dengan **software tambahan**, bisa berupa aplikasi server ataupun akses terhadap **database**. Data yang berasal dari database ini akan ditampilkan lewat ***placeholders*** yang berada pada file HTML. 

    - Proses yang terjadi pada bagian ***Server side*** adalah web server akan **menunggu *client request messages*** dalam bentuk **HTTP Request** dan akan memproses ketika pesan tersebut telah dikirimkan. Kemudian, server akan memberi respon dalam bentuk **HTTP Response message** untuk menampilkan respon yang diminta.

-   *Peserta mampu memahami konsep RESTFul API* 
    - REST merupakan singkatan dari ***REpresentational State Transfer*** merupakan **standard model arsitektur** dari sebuah sistem komputer pada web yang memudahkan komunikasi antar-sistem. Model arsitektur REST memungkinkan baik ***server*** maupun ***client*** dapat mengimplementasikan struktur mereka secara **independen** sehingga perubahan kode masing-masing sisi tidak akan saling mempengaruhi satu sama lain. 
    - Menggunakan struktur REST memungkinkan banyak *clients* untuk mengakses **REST *endpoints*** yang sama untuk memperoleh respon yang sama. 

-   Komunikasi Antara Client dan Server
    - Untuk memulai komunikasi, client akan mengirim **HTTP request** dengan yang terdiri atas **HTTP *verb***, ***header***, ***path***, dan ***optional message***. 
        - **HTTP *verb*** merupakan **perintah** untuk melaksanakan proses tertentu. Terdiri atas **GET** (untuk mendapatkan data yang diminta), **POST** (untuk menambahkan data), **PUT** (untuk melakukan pembaharuan data dengan menggunakan `id`), dan **DELETE** (menghapus data spesifik dengan `id` tertentu).
        - ***Header and Accept Parameters*** merupakan **tipe data** yang diminta oleh client. *Accept Parameters* memastikan agar server tidak mengirimkan data yang tidak dapat diterima oleh client
        - ***Path*** merupakan **struktur** yang wajib disertakan untuk mengoperasikan HTTP request. Dengan adanya *path*, maka client dapat mengetahui proses yang terjadi dan respon yang didapatkan. 

## **Day 2 : Intro NodeJS**
Learning Objective untuk *Intro NodeJS*:
-   *Peserta mampu memahami fundamental Node.js*  

    - **NodeJS** merupakan tools yang dapat digunakan untuk mengeksekusi kode sumber JavaScript pada ***V8 engine*** di luar web browser bagi *server-side scripting* untuk menciptakan ***dynamic web page*** sebelum diterima oleh pihak client.            
    - NodeJS memiliki arsitektur ***Single-Thread***, yang artinya **mampu mengeksekusi perintah** dalam satu tumpukan kode. Manajemen tumpukan kode ini disebut sebagai ***Call Stack*** layaknya sebuah antrian eksekusi. Ketika terdapat perintah baru, maka perintah tersebut akan ditambahkan `(push)` dan ditampung dalam ***event queue***. Jika sudah selesai maka perintah akan dikeluarkan `(pop)`. Siklus ini dijalankan oleh ***event loop***.

-   *Peserta mampu memahami topik utama Node.js untuk kebutuhan back-end*

    Untuk dapat memanfaatkan NodeJS untuk kebutuhan back-end, maka sudah tersedia ***build-in module*** yang dapat digunakan seperti berikut ini:
    - ***Console*** merupakan modul bawaaan dari JavaScript untuk **debug** atau **menampilkan kode** pada interface
    - ***Process*** merupakan modul yang digunakan untuk menampilkan dan mengontrol proses NodeJS yang sedang dijalankan  
    - ***OS*** merupakan modul yang digunakan untuk menyediakan informasi mengenai sistem operasi komputer yang digunakan
    - ***Util*** merupakan modul bantu untuk mendukung kebutuhan internal API
    - ***Events*** merupakan modul yang membantu untuk memberikan respon terhadap events yang diberikan oleh user, misal klik mouse atau klik pada keyboard
    -  ***Errors*** merupakan modul untuk mendefinisikan error pada NodeJS dan ditampilkan secara informatif, serta mendukung untuk mengatasi error tersebut dengan `try catch`. 
    - ***Buffer*** merupakan modul untuk mengakses, mengelola, dan mengubah tipe data raw
    - ***FS*** merupakan modul untuk membantu berinteraksi dengan file eksternal, misal .txt, .csv, maupun .json
    - ***Timers*** merupakan modul untuk melakukan **scheduling pemanggilan fungsi** pada waktu tertentu yang dapat diatur

## **Day 3 : Express Routing & Middleware**
Learning Objective untuk *Express Routing & Middleware*:
-   *Peserta mampu memahami dan membuat routing*
    -   ***Route*** merupakan **end-point** yang diakses menggunakan URL. Route memiliki struktur berupa ***method* API, alamat, dan respon** yang perlu ditampilkan. Misal,
            
            app.get('/', (req, res) => {
                res.send('Hello World!')
            })
        Pada contoh di atas, `get` merupakan ***method* API** yang digunakan. Kemudian, `'/'` merupakan **alamat**, serta `res.send('Hello World!')` merupakan **respon** yang diberikan. Selain itu, perlu juga memberikan **status code** untuk menginformasikan apakah route yang diakses dapat berjalan dengan baik. 

    -    Kemudian, terdapat **query** yaitu parameter untuk membantu menentukan tindakan yang diminta secara lebih spesifik. Biasanya, query berada di akhir route dengan diawali `"?"` kemudian dilengkapi dengan key dan data yang diminta.    

-   *Peserta mampu memahami dan membuat middleware*
    -   **Middleware** merupakan fungsi yang memiliki akses ke **objek** pada request maupun response dan juga **next function** pada sebuah *request-response cycle*. Misal, 
            
            app.get('/', function(req,res,next) {
                next();
            })
            app.listen(3000);

    -   Secara garis besar, **fungsi Middleware** berfungsi layaknya ***filter*** terhadap HTTP request yang dikirim oleh client untuk diproses lebih lanjut oleh server. Jika middleware mendapati terdapat HTTP request yang tidak sesuai, maka middleware dapat **menghentikan** *request-response cycle*. 
    -  Selain itu, fungsi Middleware juga memungkinkan untuk **menjalankan kode**, **menambahkan informasi pada object request maupun object response**, **melanjutkan request ke handler function** dengan menggunakan `next()` seperti pada contoh di atas. 
    - Selanjutnya, fungsi Middleware dapat dibedakan berdasarkan cara penggunaan, yaitu
        - **Application Level Middleware** yang mana fungsi middleware melekat pada ***instance object application express*** dan akan dijalankan saat aplikasi Express **menerima HTTP request** dari client
        - **Router Level Middleware** yang mana fungsi middleware melekat pada ***instance object router express*** dan akan dijalankan saat express router dengan fungsi middleware ini **menerima HTTP request** dan router lain **tidak dijalankan**. 
        - **Error Handling Middleware** yang mana fungsi middleware akan dijalankan ketika aplikasi express **menangkap dan memproses** error yang terjadi. Yang perlu diperhatikan adalah error handling perlu **empat buah argumen** yaitu `(err, req, res, next)` agar dapat dideteksi oleh aplikasi express sebagai **error handling middleware**. 
## **Day 4-5 : Design Databases**
Learning Objective untuk *Design Databases*:    
-   *Peserta mampu menentukan dan membuat diagram entity*
    
    -   Pada sebuah database, terdapat **entiti** yang merupakan scoop paling umum dari requirement yang diberikan, misal mahasiswa, dosen, kelas, atau mata kuliah. 

-   *Peserta mampu menentukan dan membuat attribute entity*

    -   Dari entiti tersebut, terdapat anggota atau bagian yang mengisi entitas yang ada, misal untuk entitas mahasiswa memiliki NIM, dosen memiliki NIP, kelas memiliki kode kelas FA, atau mata kuliah memiliki nama matkul kimia_dasar. Anggota atau bagian tersebut kita sebut sebagai **atribut** dari entitas

-   *Peserta mampu menentukan dan membuat relasi entity*
    -   **Relasi** menunjukkan hubungan yang terbentuk antar-entitas. Misal, mahasiswa dapat memilih banyak mata kuliah, sedangkan dosen harus mengajar satu mata kuliah spesialis. Relasi yang terbentuk antara mahasiswa dengan mata kuliah adalah contoh dari ***Many-to-Many***, sedangkan relasi antara dosen dengan mata kuliah disebut sebagai ***One-to-One***. Misal, satu ruang kelas biasanya digunakan untuk seluruh mata kuliah, maka relasi yang terbentuk adalah ***One-to-Many***      
