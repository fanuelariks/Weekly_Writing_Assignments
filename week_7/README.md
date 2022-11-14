# Writing Test Week 7   
## **Day 1 : Sequalize**
Learning Objective untuk *Sequalize*:    
-  *Peserta mampu memahami dan menggunakan Sequalize*
    
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

-   *Peserta mampu membuat API Specification*

    -   Untuk membuat suatu spesifikasi API, maka programer dapat menyusun kode seperti contoh berikut:

            const express = require('express');
            const router = express.Router()

            const usersRouter = require("./user.router")
            router.use("/users", usersRouter)

            module.exports = router  

    -   Setelah itu, dapat dirancang endpoint yang diperlukan misal seperti berikut:
                
            module.exports = {
                getAlluser: (req, res) => {

                },
                getUserById: (req, res) => {

                },
            
                addUser: (req, res) => {
            
                },
            
                deleteUserByID: (req, res) => {
            
                },
            
                updateUserByID: (req, res) => {
            
                },
            }      

## **Day 2 : MongoDB**
Learning Objective untuk *MongoDB*:
-   *Peserta mampu memahami basic dari MongoDB*
    
    -   MongoDB merupakan salah satu database yang sering digunakan untuk aplikasi berbasis Cloud, Big Data, maupun Grid Computing. 
    -   MongoDB menyimpan dokumen dengan format JSON secara fleksibel dan tidak membutuhkan query layaknya SQL, sehingga memungkinkan untuk menampung banyak data yang bervariasi           
    -   Namun, MongoDB juga memiliki kekurangan dengan menggunakan cukup banyak memory dan hanya mampu menampung maksimal 16 MB tiap dokumen

## **Day 3 : Mongoose**
Learning Objective untuk *Mongoose*:
-   *Peserta mampu memahami basic dari Mongoose* 
    -   Mongoose merupakan library sebagai Objcet Modelling MongoDB untuk NodeJS dan digunakan untuk mengelola relasi data 
    -   Untuk installasi dapat digunakan
            
            npm install mongoose
         
## **Day 4 : Mongoose**
Learning Objective untuk *Docker*:
-   *Peserta mampu memahami container pada Docker* 
    -   Container memungkinkan docker untuk berbagi host OS agar aplikasi dapat dijalankan di mana saja dan kapan saja
    -   Container memungkinkan aplikasi yang dijalankan tidak terpengaruh oleh faktor luar
    -   Selain itu, container juga melakukan virtualisasi pada hos OS

-   *Peserta mampu memahami dan menggunakan basic dari Docker*  
    -   Untuk instalasi dapat digunakan

            start /w "" "Docker Desktop Installer.exe" install          