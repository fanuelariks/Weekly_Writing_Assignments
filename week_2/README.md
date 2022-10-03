# Writing Test Week 2
## **Day 1 : Javascript Dasar (*Scope and Function*)**
Learning Objective untuk *Scope and Function*:
-   *Peserta mampu memahami scope*  

    Pada umumnya, scope pada Javascript terdiri atas:
    
    -   ***Block Scope*** yang menggunakan *keywords* berupa ***let*** dan ***const*** yang memungkinkan deklarasi variabel di dalam *bracket*. Misal,

            {
                let x = 2;
            }
            // x tidak dapat diakses di luar bracket

         Tetapi, perlu diperhatikan jika kita ingin menggunakan ***block scope***, kita tidak bisa menggunakan *keywords* berupa ***var***. Misal, 

            {
                var x = 2;
            }        
            // x dapat diakses di luar bracket karena var tidak dapat digunakan di scope ini

    -   ***Local Scope*** merupakan scope yang dideklarasikan di dalam sebuah fungsi, sehingga scope tersebut hanya dapat diakses di dalam fungsi. Misal,

            function namaMobil() {
                let mobil = 'BMW'
                // hanya bisa diakses di dalam fungsi
            }
            // di luar fungsi, scope tersebut tidak dapat diakses

        Pada contoh tersebut, **let mobil = 'BMW'** dapat disebut juga sebagai ***function scope***

    -   ***Global Scope*** merupakan scope yang dideklarasikan di luar fungsi sehingga memungkinkan diakses dari manapun. Misal, 

            let x = 2;

-   *Peserta mampu memahami dan membuat fungsi*

    **Fungsi** mudahnya merupakan kelompok kode yang digunakan untuk mengerjakan tugas khusus untuk menyelesaikan suatu kasus berulang. *Syntax*-nya secara sederhana seperti berikut:

        function name(parameter1, paramater2, parameter3) {
            //kode yang akan dikerjakan
        }

    di mana **parameter** merupakan batasan masukan yang diterima oleh fungsi, kemudian **name** merupakan identifikasi fungsi untuk dapat digunakan kembali pada pemanggilan fungsi berikutnya. Berikut adalah contoh penerapan fungsi:

        function toko(pembeli, produk){
            return 'Terimakasih ' + pembeli + ' telah membeli produk ' + produk;
        }
        console.log(toko('Joko', 'Buah Semangka'));

    Jika diperhatikan, maka fungsi akan mengembalikan nilai yang diberikan oleh **parameter**. Pada contoh, **return** akan mengembalikan nilai dari paramater **pembeli** dan **produk**. Kemudian, di bagian 
        
        console.log(toko('Joko', 'Buah Semangka'));
    
    terdapat **argumen**, yaitu nilai parameter yang diberikan kepada fungsi. Jadi, parameter **pembeli** diberikan nilai **"Joko"** dan parameter **produk** diberi nilai **"Buah Semangka"**.  

    Kemudian, terdapat cara penulisan yang baru dikenalkan pada versi Javascript ES6, yaitu ***Arrow Function*** dengan *syntax* seperti berikut:

        //Versi Fungsi biasa

        hello = function() {
            return "Hello World";
        }

        //Versi Arrow Function

        hello = () => {
            return "Hello World";
        }

    Jika kita gunakan ***Arrow Function*** tersebut pada contoh produk dan pembeli sebelumnya, maka akan menjadi seperti berikut:

        toko = (pembeli, produk) => {
            return 'Terimakasih ' + pembeli + ' telah membeli produk ' + produk;
        } 
        console.log(toko('Joko', 'Buah Semangka'));   

## **Day 2 : *Data Type Built in Prototype & Method***
Learning Objective untuk *Data Type Built in Prototype & Method*:

-   *Peserta mampu memahami tipe data yang ada pada Javascript*

    Secara garis besar, tipe data pada Javascript dibedakan menjadi tipe ***Primitive Values*** dan ***Objects***. Untuk dapat mengetahui apakah variabel yang ada merupakan salah satu dari tipe data tersebut, dapat digunakan kode (```typeof```). Berikut adalah penjelasan secara singkat dari keduanya. 

    1. ***Primitive Values*** merupakan tipe data yang sifatnya tidak dapat dirubah atau disebut sebagai ***immutable values***. Contoh dari *primitive values* sebagai berikut

        - ***Boolean*** merupakan tipe data yang sifatnya logika dan hanya memiliki dua nilai, yaitu **true** maupun **false**. *Boolean* ini merupakan tipe data logika yang seringkali digunakan untuk mendefinisikan suatu keadaan untuk menjalankan kode yang dirancang, misal untuk *if statements* atau *for loops*. 

        - ***Null*** merupakan tipe data yang memiliki satu nilai, yaitu **null**. Keberadaan nilai **null** merupakan aksi yang disengaja untuk menyisipkan nilai **null** pada variabel tertentu. 

        - ***Undefined*** merupakan tipe data berupa properti dari *global object* yang menunjukkan tidak terdefinisinya suatu milai pada objek atau variabel. Fungsi akan mengembalikan nilai **undefined** jika tidak ditemukan nilai pada suatu objek.   

        - ***Number*** merupakan tipe data bilangan yang mampu menyimpan nilai float di antara 2^-1074 (```Number.MIN_VALUE```) dan 2^1024 (```Number.MAX_VALUE```) juga untuk nilai -(2^-1074) serta -(2^1024). Salah satu cara untuk memastikan tipe data tersebut adalah ***number*** yaitu dengan menggunakan ```Number.isNaN()```. 

        - ***String*** merupakan tipe data berbentuk teks yang mana setiap elemennya memiliki posisi, dimulai dari index ke-0, sehingga panjang dari *string* tersebut sama dengan jumlah elemen yang ada di dalamnya. Untuk dapat mengetahui panjang *string*, programmer dapat menggunakan kode ```length```, kemudian bisa juga mendapatkan elemen karakter pada posisi tertentu dengan kode ```charAt()```. Data berupa angka juga dapat diubah menjadi *string* dengan menggunakan kode ```toString()```.

    2. ***Objects*** merupakan tipe data yang mana berupa kumpulan properti. Secara umum, properti ini akan berhubungan dengan atribut yang akan diakses secara langsung oleh program Javascript. Namun, programmer dapat mengakses properti tersebut dengan kode ```Object.defineProperty()```.    

    Selain itu, terdapat pula objek ***Math*** yang memiliki properti dan metode untuk konstanta maupun fungsi matematis, yang mana akan bekerja dengan tipe data **Number**. Berikut adalah beberapa contoh dari properti dari **Math**:

    -   **Math.E** yang akan mengeluarkan nilai konstanta *euler* senilai 2,718

    - **Math.LN2** berupa *natural logarithm* dari 2 senilai 0,693 

    - **Math.PI** yang akan mengeluarkan nilai *phi* senilai 3,14159

    - **Math.SQRT2** yang akan mengeluarkan nilai akar 2 senilai 1,414

    Selain itu, terdapat metode-metode yang dapat digunakan dalam objek **math**. Berikut adalah contohnya:

    - **Math.abs()** yang akan mengembalikan nilai absolut dari ```x```

    - **Math.acos()** yang akan mengembalikan nilai dari *arccosine* dari ```x```

    - **Math.asin()** yang akan mengembalikan nilai dari *arcsine* dari ```x``` 

    - **Math.atan()** yang akan mengembalikan nilai dari *arctangent* dari ```x```

    - **Math.cos()** yang akan mengembalikan nilai dari *cosine* dari ```x```

    - **Math.exp()** yang akan mengembalikan nilai dari *euler* dari ```x```

    - **Math.log()** yang akan mengembalikan nilai dari log dari ```x```

    - **Math.sin()** yang akan mengembalikan nilai dari *sine* dari ```x```

    - **Math.sqrt()** yang akan mengembalikan nilai dari akar persegi dari ```x```
    
    - **Math.tan()** yang akan mengembalikan nilai dari *tangent* dari ```x```

## **Day 3 : JavaScript-DOM**
Learning Objective untuk JavaScript DOM:

-   *Peserta mampu memahami dan memanipulasi konten HTML dengan DOM*

    Secara umum, pengertian dari *Document Object Model* (DOM) merupakan sebuah *Application Programming Interface* (API) yang dapat digunakan untuk memanipulasi HTML. 

    HTML digambarkan sebagai sebuah dokumen dengan ***nodes*** dan ***elements*** yang ada di dalamnya, membentuk struktur hirarki layaknya sebuah pohon. Ilustrasi bisa didapatkan dari [javascripttutorial.net](https://www.javascripttutorial.net/javascript-dom/document-object-model-in-javascript/).

    Seringkali, terjadi kebingungan mengenai perbedaan antara **node** dan **element**. Sederhananya, **node** merupakan bentuk objek secara umum dari DOM (istilahnya adalah ***generic name***), ditandai dengan tag HTML misal ```<div>``` atau ```<p>```. Sedangkan **element** merupakan *node* tipe khusus, misal ditandai dengan ```<input type='_'>```. Itulah mengapa, ketika kita memanggil ```getElementById()``` atau ```querySelector()``` akan mengembalikan tipe objek yaitu **element**. Sedangkan ketika memanggil ```getElememtsByTagName()``` atau ```querySelectorAll()``` akan mengembalikan objek **node**. 

    Berikutnya, kita akan membahas mengenai **cara untuk memanggil elemen** dan **memanipulasi elemen tersebut**.

    1. ***Selecting Elements*** di mana kita akan belajar mengenai cara untuk memanggil elemen yang akan dimanipulasi. Berikut adalah beberapa caranya:
    
        -   ***getElementById()***. Metode ini akan mengembalikan objek tipe elemen dengan *id* tertentu yang terdapat pada dokumen HTML. Jika tidak teridentifikasi *id* yang sesuai, maka metode ini akan mengembalikan nilai ***null***. Berikut adalah contoh penggunaan syntax yang sering digunakan.

                //dokumen HTML
                <html>
                    <head>
                        <title>Coba JavaScript</title>
                    </head>
                    <body>
                        <p id="pesan">Sebuah Pesan</p>
                    </body>
                </html>

            Pada contoh dokumen HTML di atas, terdapat elemen ```<p>``` dengan **id** berupa **pesan**

                //DOM JavaScript
                const p = document.getElementById('pesan');
                console.log(p);

            Output yang dihasilkan

                //Output
                <p id="pesan">Sebuah Pesan</p>    

        -   ***getElementByName()***. Metode ini akan mengembalikan objek tipe elemen dengan *name* tertentu yang terdapat pada dokumen HTML. Secara umum, penggunaan ***getElementByName()*** serupa dengan *getElementById()*. Berikut adalah contohnya. 

                //dokumen HTML
                <input type='radio' name='language' value='JavaScript>

            Pada contoh dokumen HTML di atas, terdapat elemen ```<input>``` dengan **name** berupa **language**

                //DOM JavaScript
                let elements = document.getElementsByName('language');

        -   ***getElementByTagName()***. Metode ini akan memanggil elemen yang memiliki **tag name** sesuai dengan yang diminta, kemudian akan mengembalikan ***HTML Collection*** dalam bentuk seperti *array* yang sesuai dengan *tag name* yang diminta. Berikut adalah syntax yang digunakan:

                let elements = document.getElementsByTagName(tagName);

        -   ***getElementsByClassName()***. Metode ini akan mengembalikan objek tipe *child-element* dengan ***class*** sesuai dengan yang diminta. Berikut adalah contoh penggunaan syntax-nya

                //dokumen HTML
                <nav>
                    <ul id="menu>
                        <li class='item'>HTML</li>
                        <li class='item'>CSS</li>
                        <li class='item'>JavaScript</li> 
                    </ul>
                </nav>                   

            Pada dokumen HTML di atas, terdapat id **menu** dan class **item**. 

                //DOM JavaScript
                let menu = document.getElementById('menu');
                let items = menu.getElementsByClassName('item');

                let data = [].map.call(items, item => item.textContent);

                console.log(data);

            Kemudian, pada DOM akan dipanggil **id** sebagai ***parent-element*** untuk kemudian memanggil **class** sebagai ***child-element*** dan menyimpan data-data yang diperoleh dalam variabel **data**. 

                //Output
                ['HTML', 'CSS', 'JavaScript']

        -   ***querySelector()***. Metode ini digunakan untuk memanggil elemen pada dokumen HTML yang sesuai dengan selektor pada CSS untuk memanipulasi tampilan atau *interface*. Selain menggunakan **querySelector()**, programmer juga bisa menggunakan ***querySelectorAll()*** untuk memanggil *semua* elemen yang sesuai dengan *CSS Selector*. Untuk itu, penting bagi programmer memahami **selektor** dasar yang dapat digunakan untuk memanggil elemen pada HTML. Berikut adalah beberapa di antaranya.

            1. **Universal Selector** merupakan selektor yang dapat memanggil seluruh elemen yang ada, ditandai dengan ```*```. Contoh dari penggunaannya, yaitu:

                    let element = document.querySelector('*'); 

            2. **Type Selector** merupakan selektor yang memanggil elemen HTML berdasarkan tag pada *node* yang ada. Misal, 

                    let element = document.querySelector('h1');

            3. **Class Selector** merupakan selektor yang memanggil elemen HTML berdasarkan kelas CSS yang telah diberikan. Contoh dari sintaksnya yaitu:

                    let element = document.querySelector('.item');

            4. **ID Selector** merupakan selektor yang memanggil elemen HTML berdasarkan *id* yang telah disematkan. Contoh dari sintaks yang digunakan:

                    let element = document.querySelector('#pesan');

            5. **Descendant Combinator** merupakan selektor yang memanggil elemen HTML berdasarkan hirarki tag yang ada. Misal, untuk memanggil semua tag ```<a>``` yang berada di dalam tag ```<head>```, maka dapat digunakan sintaks berikut:

                    let element = document.querySelector('head a'); 

            6. **Child Combinator** merupakan  selektor yang memanggil elemen HTML berdasarkan hirarki ***parent-and-child***. Misal, untuk memanggil elemen ```<a>``` yang ada di dalam elemen ```<p>```, maka dapat digunakan sintaks berikut:

                     let element = document.querySelector('p > a'); 

    2.  ***Traversing Elements*** di mana kita akan belajar mengenai cara untuk mencari tahu keberadaan elemen HTML berdasarkan relasinya dengan elemen HTML lain. Berikut adalah beberapa caranya:                 
        
        -   ***Get the Parent Node*** di mana kita dapat mengetahui *parent* dari sebuah elemen HTML dengan menggunakan kode ```parentNode```. Berikut adalah contoh dari penggunaan sintaksnya:

                <body>
                    <div id="main">
                        <p class="note">This is a note!</p>
                    </div>

                    <script>
                        let note = document.querySelector('.note');
                        console.log(note.parentNode);
                    </script>
                </body>

            Dengan menggunakan kode tersebut, maka kita akan peroleh keluaran berupa *parent* dari *class* ```"note"``` seperti berikut:

                <div id="main">
                    <p class="note">This is a note!</p>
                </div>

        -   ***Get the Child Elements of Node*** di mana kita dapat mengetahui elemen *child* pertama dan yang terakhir. Berikut adalah penjelasan singkatnya.

                <ul id="menu">
                    <li class="first">Home</li>
                    <li>Products</li>
                    <li class="current">Customer Support</li>
                    <li>Careers</li>
                    <li>News</li>
                    <li class="last">About Us</li>
                </ul>

            Untuk mengetahui elemen pertama yang terkandung, dapat digunakan properti ```firstElementChild``` seperti berikut:

                //Penggunaan properti
                let content = document.getElementById('menu');
                let firstchild = content.firstElementChild

                console.log(firstchild);

                //Output yang dihasilkan
                <li class="first">Home</li>

            Untuk mengetahui elemen terakhir yang terkandung, dapat digunakan properti ```lastElementChild``` dengan sintaks seperti berikut:

                //Penggunaan properti
                let content = document.getElementById('menu');
                console.log(content.lastElementChild);

                //Output
                <li class="last">About Us</li>

        -   ***Get the Sibling Elements of Node*** di mana kita dapat mengetahui elemen setelah elemen tertentu. Berikut adalah penjelasan singkatnya.

                <ul id="menu">
                    <li class="first">Home</li>
                    <li>Products</li>
                    <li class="current">Customer Support</li>
                    <li>Careers</li>
                    <li>News</li>
                    <li class="last">About Us</li>
                </ul>

            Untuk mengetahui elemen **setelah** elemen tertentu, dapat digunakan properti ```nextElementSibling``` seperti berikut:

                //Penggunaan properti
                let content = document.querySelector('.current');
                let nxt_sibling = content.nextElementSibling;

                console.log(nxt_sibling);

                //Output yang dihasilkan
                <li>Careers</li>

            Untuk mengetahui elemen **sebelum** elemen tertentu, dapat digunakan properti ```previousElementSibling``` seperti berikut:

                //Penggunaan properti
                let content = document.querySelector('.current');
                let prev_sibling = content.previousElementSibling;

                console.log(prev_sibling);

                //Output yang dihasilkan
                <li>Products</li>    

## **Day 4 : JavaScript-DOM (Lanjutan)**                
Pada hari keempat ini, kami belajar mengenai ***Manipulating Elements and Styles***. Berikut adalah penjelasannya. 

1.  ***Manipulating Elements*** merupakan metode yang dapat digunakan untuk memanipulasi elemen yang ada pada HTML. Berikut adalah metode-metode yang dapat dilakukan.

    -   **createElement()** digunakan untuk membuat sebuah elemen HTML baru dan menggabungkannya pada dokumen HTML. Sintaks dasarnya adalah

            let element = document.createElement(htmlTag);

        Dengan menggunakan sintaks tersebut, kita dapat membuat sebuah elemen baru, misal untuk membuat elemen **div** baru

            let div = document.createElement('div');

        Kemudian, untuk mengisi konten pada elemen tersebut, dapat digunakan sintaks

            div.innerHTML = '<p>Membuat Elemen Baru</p>';

        Misal, jika ingin menambahkan **id** serta **class** pada elemen baru tersebut, kita dapat menggunakan sintaks berikut:

            //Menambahkan ID dan Class
            let div = document.createElement('div');
            let div.id = 'content';
            let div.className = 'note';
            let div.innerHTML = '<p>Membuat Elemen Baru</p>';

        Terakhir, jika kita ingin menambahkan elemen baru pada elemen tadi, maka kita dapat menggunakan sintaks berikut:

            let div = document.createElement('div');
            let div.id = 'content';
            let div.className = 'note';

            //Menambahkan elemen baru
            let h2 = document.createElement('h2');
            h2.textContent = 'Menambahkan elemen h2 pada elemen div'
            div.appendChild(h2);

    -   **innerHTML** dapat digunakan untuk mengakses maupun mengedit elemen yang ada pada dokumen HTML. Berikut adalah contoh penggunaan sintaksnya:

            <ul id='menu'>
                <li>Halo</li>
                <li>Kita ada di sini</li>
            </ul>         

            //Untuk membaca elemen yang ada di dokumen                
            let menu = document.getElementById('menu');
            console.log(menu.innerHTML);

            //Output
            <li>Halo</li>
            <li>Kita ada di sini</li>

        Selain untuk membaca list elemen yang ada, ```innerHTML``` dapat juga digunakan untuk memanipulasi elemen yang ada. Misal,

            let menu = document.getElementById('menu')
            let li = document.createElement('li')

            //Untuk menambahkan konten pada <li>#1
            li.textContent = 'Lagi coba innerHTML';
            menu.appendChild(li);
            console.log(menu.innerHTML);

            //Untuk menambahkan konten pada <li>#2
            menu.appendChild(li);
            li.innerHTML = 'Lagi coba innerHTML';
            console.log(menu.innerHTML);

    -   **appendChild()** dapat digunakan untuk menambahkan node pada dokumen HTML. Seperti contoh pada ```createElement()``` dan ```innerHTML``` di mana ```appendChild()``` digunakan untuk menambahkan **node** baru serta konten yang ada di dalamnya.

    -   **append()** dapat digunakan juga untuk menambahkan node pada dokumen HTML **serta** DOMString. Berbeda dengan ```appendChild()``` yang hanya mampu **menambahkan node** pada dokumen HTML. Berikut adalah contoh sintaks sederhana dari ```append()``` 

            let li = document.createElement('li') 
            li.append('Lagi coba append nih');

2.  ***Manipulating Styles*** merupakan metode yang dapat digunakan untuk memanipulasi *style* pada elemen HTML. Berikut adalah metode-metode yang dapat dilakukan.   

    -   **JavaScript Style** merupakan properti yang digunakan untuk mengatur *style* dari sebuah elemen HTML. Berikut adalah sintaks yang dapat digunakan

            element.style.property = 'style';

        Misal, untuk dapat memanipulasi satu elemen, maka dapat digunakan sintaks:

            element.style.cssText = 'color:red';    

        Atau untuk menambahkan style tertentu pada suatu elemen, dapat digunakan sintaks:

            element.style.cssText += 'color:red';  

    -   **className** merupakan properti yang digunakan untuk mendapatkan nama *CSS class* dari sebuah elemen dan memanipulasinya. Berikut adalah contohnya.

            <ul id='menu' class='vertical main'>
                <li>Tampak Depan</li>
                <li>Tampak Belakang</li>
                <li>Tampak Samping</li>
            </ul>              

            // Untuk mendapatkan nama kelas dari elemen tersebut

            let nama = document.querySelector('#menu');
            console.log(menu.className);

            // Output
            
            vertical main

        Untuk menambahkan nama di atas, maka dapat digunakan sintaks

            // Untuk mendapatkan nama kelas dari elemen tersebut

            let nama = document.querySelector('#menu');
            menu.className += 'new'
            console.log(menu.className);

            // Output
            
            vertical main new

    -   **offsetWidth and offsetHeight** merupakan properti yang digunakan untuk mendapatkan tinggi serta lebar dari konten, termasuk *padding* dan *border*. Berikut adalah contoh penggunaan sintaksnya

            <body>
                <div class="box" style="width:100px;height:150px;border:solid 1px #000;padding:10px"></div>

                //Penggunaan offsetWidth dan offsetHeight
                <script>
                    let box = document.querySelector('.box');
                    let width = box.offsetWidth;
                    let height = box.offsetHeight;
                    console.log({ width, height });
                </script>
            </body>

            //Output
            {width: 122, height: 172}   

        Untuk mendapatkan nilai tinggi dan lebar serta *padding* **tanpa** border, maka dapat digunakan sintax ```clientWidth``` dan ```clientHeight```. 

## **Day 5 : JavaScript-DOM (Lanjutan)**                
Pada hari kelima ini, kami belajar mengenai ***Events and Forms***. Berikut adalah penjelasannya. 

1.  ***Events*** merupakan aksi yang diberikan oleh website sebagai bentuk feedback atas aksi yang user berikan sehingga user dapat kembali memberi respon terhadap feedback dari website. Berikut adalah salah satu event yang terjadi.

    -   **Page Load Events** merupakan aksi yang terjadi ketika ***load page*** dan terjadi beberapa aksi. Ketika kita membuka website, akan terjadi aksi:
        
        -   ```DOMContentLoaded``` merupakan aksi ketika website pertama kali dibuka dan mampu me-*load* dokumen HTML, namun belum dengan konten eksternal, seperti gambar. Pada aksi ini, programmer dapat memulai untuk ***initialize*** antarmuka yang ada.

        -   ```load``` merupakan aksi ketika website berhasil di-*load* sepenuhnya, termasuk dengan konten eksternal tambahan.

        Ketika kita menutup website, maka akan terjadi aksi seperti berikut:

        -   ```beforeunload``` merupakan aksi yang mengawali *unloading* dokumen HTML serta konten yang ada. Biasanya, akan ditandai dengan *dialog box* yang membantu user untuk tidak kehilangan data personal ketika akan meninggalkan laman website.

        -   ```unload``` merupakan aksi yang terjadi ketika dokumen HTML dan konten yang ada dalam website berhasil di-*unload* sepenuhnya. 

    Selanjutnya, ada beberapa events yang dapat ditangkap oleh HTML DOM, di antaranya ```change```, ```focus```, ```hover```, ```click```, ```blur```, ```scroll```, dan ```submit```. Untuk dapat menerima interaksi yang diberikan oleh user, maka kita dapat menggunakan metode ```addEventListener()```. Berikut adalah contoh sintaks sederhana.

        let btn = document.querySelector('#btn');

        pesan = () => {
            alert('Anda menekan klik!')
        }       

        btn.addEventListener('click', pesan);

    Pada dasarnya, terdapat aliran aksi (*event flow*) yang menunjukkan adanya keteraturan alur aksi ketika diberikan oleh user maupun respon feedback dari website. ***Event Flow*** terdiri atas dua event utama, yaitu

    1.  **Event Bubbling**, di mana aksi dimulai pada elemen spesifik pada dokumen HTML yang diberikan oleh user. Misal, pada contoh di atas, user akan memasukkan aksi "klik" pada tombol. Aksi akan bergerak ke hirarki DOM paling atas sesuai dengan urutan elemen yang ada hingga mencapai dokumen. 

    2.  **Event Capturing**, di mana aksi akan bergerak dengan arah berbanding terbalik dari *event bubling* yang mana akan mulai bergerak dari hirarki elemen paling awal menuju akhir. 

 2. ***Forms*** merupakan aksi yang diberikan oleh user untuk mengisi suatu form dan bagi website untuk menerima data yang telah diinput oleh user. Misal, programmer membangun website yang dapat memberi input berupa nama dan email dengan sintaks berikut.

        <form id="form">
            <div class="nama">
                <input type='text' name='nama'/>
            </div>
            <div class="email">
                <input type='text' name='email'/>
            </div>
        </form>

    Untuk dapat mengambil data dari kedua input di atas, programmer dapat menggunakan sintaks berikut:

        let form = document.getElementById('form');

        form.addEventListener('submit', event = () => {
            //untuk mencegah refresh page
            event.preventDefault();

            const formData = new FormData(form)
            const values = Object.fromEntries(formData)
        } )           

    Penggunaan sintaks ```fromEntries()``` memungkinkan program untuk mengambil data berupa *array* dari **formData** untuk dikembalikan menjadi objek.

                