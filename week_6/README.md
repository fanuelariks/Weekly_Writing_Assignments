# Writing Test Week 6
## **Day 1 : Design Database (Lanjutan)**
Learning Objective untuk *Design Databases*:    
-   *Peserta mampu menentukan dan membuat diagram entity*
    
    -   Pada sebuah database, terdapat **entiti** yang merupakan scoop paling umum dari requirement yang diberikan, misal mahasiswa, dosen, kelas, atau mata kuliah. 

-   *Peserta mampu menentukan dan membuat attribute entity*

    -   Dari entiti tersebut, terdapat anggota atau bagian yang mengisi entitas yang ada, misal untuk entitas mahasiswa memiliki NIM, dosen memiliki NIP, kelas memiliki kode kelas FA, atau mata kuliah memiliki nama matkul kimia_dasar. Anggota atau bagian tersebut kita sebut sebagai **atribut** dari entitas

-   *Peserta mampu menentukan dan membuat relasi entity*
    -   **Relasi** menunjukkan hubungan yang terbentuk antar-entitas. Misal, mahasiswa dapat memilih banyak mata kuliah, sedangkan dosen harus mengajar satu mata kuliah spesialis. Relasi yang terbentuk antara mahasiswa dengan mata kuliah adalah contoh dari ***Many-to-Many***, sedangkan relasi antara dosen dengan mata kuliah disebut sebagai ***One-to-One***. Misal, satu ruang kelas biasanya digunakan untuk seluruh mata kuliah, maka relasi yang terbentuk adalah ***One-to-Many***      

## **Day 2 : MySQL (Lanjutan)**
Learning Objective untuk *MySQL (Lanjutan)*:
-   *Peserta mampu memahami dan melakukan manipulasi query tingkat lanjut yang sering digunakan* 
    -   Secara umum, query pada SQL akan dimulai dengan `SELECT *`. Untuk itu, akan dicontohkan beberapa query yang sering digunakan.   
       
            CREATE TABLE product (
                id INT PRIMARY KEY NOT NULL AUTO_INCREMENT,
                name VARCHAR(50),
                price INT,
                category_id INT,
                FOREIGN KEY (category_id)
                    REFERENCES category (id)
            );

            insert into product (name, price, category_id) VALUES
                ("nasi goreng", 20000, 1),
                ("es buah", 10000, 2),
                ("pisang goreng", 5000, 3),
                ("kentang goreng", 12000, 3),
                ("es alpokat", 8000, 2),
                ("nasi hainan", 25000, 1),
                ("es doger", 5000, 3),
                ("pizza", 35000, 1);
            
            //Gunakan query ini untuk menampilkan data yang ada pada tabel product

            SELECT * FROM product;

            //Gunakan query ini sebagai bagian dari Aggregate Functions

            select max(price) from product; //menghitung harga tertinggi

            select sum(price) from product; //menghitung harga total
            
            select count(category_id) from product group by category_id; //menghitung jumlah kategori yang ada
            
            select avg(price) from product; //menghitung rerata harga           


-   *Peserta mampu memahami dan membuat relational antar table*
    -   Untuk membuat sebuah relasi antar-tabel, dapat digunakan metode **JOIN**. Join ini terdiri atas
        -   ***Inner Join*** di mana semua baris dari kedua tabel data akan digabungkan hanya jika memenuhi kondisi yang ditentukan. Misal, 

                SELECT product.id, product.name, product.price, category.name
                FROM product INNER JOIN
                category ON product.category_id = category.id;
            Dengan begitu, akan ditampilkan id produk, nama produk, harga, hingga kategori yang merupakan gabungan dari tabel produk dan kategori menyesuaikan dengan keadaan dari `category_id`.  

        -   ***Left Join*** di mana semua baris dari tabel data sisi kiri akan digabungkan hanya jika memenuhi kondisi yang ditentukan. 

        -   ***Right Join*** di mana semua baris dari tabel data sisi kanan akan digabungkan hanya jika memenuhi kondisi yang ditentukan.   

## **Day 3 : Authentication vs Authorization vs Encryption**
Learning Objective untuk *Authentication vs Authorization vs Encryption*:
-   *Peserta mampu memahami beberapa variasi authentication dan authorization*
    -   ***Cookies*** merupakan *key-value pair* yang tersimpan di dalam browser, dihubungkan pada setiap HTTP request yang dikirim menuju server. *Cookie* tidak dapat digunakan untuk menyimpan informasi yang cukup banyak dan sangat penting karena akan sangat mudah untuk diakses oleh pihak lain
    -   ***Session Data*** merupakan variasi lain untuk menyimpan data pada *server-side*. Untuk dapat mengakses data yang disimpan, digunakan ***session*** yang terotentikasi ataupun ***session id*** yang didapat dari ***cookies***. 
    -   **JSON *Web Tokens*** merupakan objek JSON yang dapat digunakan untuk mentransmisikan informasi yang telah diubah secara digital dengan ***private key pair***. 
-   *Peserta mampu memahami perbedaan authnentication, authorization, dan encryption*
    -   ***Authentication*** merupakan tahap verifikasi untuk membuktikan keaslian pihak yang akan masuk pada sistem. Gambaran umumnya, otentikasi seperti memverifikasi ID yang dibawa oleh user untuk masuk ke dalam sistem
    -   ***Authorization*** merupakan tahap verifikasi lebih lanjut ketika user sudah masuk pada sistem di mana sistem mengidentifikasi ***role*** apa yang dimiliki dan apa yang bisa dilakukan oleh user pada sistem
    -   ***Encryption*** merupakan tahap untuk mengubah data verifikasi yang diinput oleh user menjadi format data yang tidak mudah terbaca.
    
## **Day 5 : Sequalize**
Learning Objective untuk *Sequalize*:    
-   *Peserta mampu memahami dan menggunakan Sequalize*
    -   Sequalize adalah ORM (*Object Relational Mapping*) berbasis promise untuk membantu developer dalam mengatur data di database dengan cepat dan efisien. ORM sendiri merupakan metode untuk mengkonversi data dari bahasa pemrogramman berbasis objek
    -   Untuk dapat menggunakan sequalize, kita perlu melakukan instalasi Sequalize dengan kode seperti berikut

            npm install --save sequelize
            npm install --save mysql 
            npm sequelize-cli init

            const Sequelize = require('sequelize');
            const sequelize = new Sequelize({
            // The `host` parameter is required for other databases
            // host: 'localhost'
            dialect: 'sqlite',
            storage: './database.sqlite'
            });       