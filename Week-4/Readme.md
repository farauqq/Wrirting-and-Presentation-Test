# Writing and Presentation Test Week 4
## Javacript Intermediate - Asynchronous Fetch 
- Dalam melakukan network request, JavaScript memiliki metode bernama fetch().
- Proses melakukan fetch() adalah salah satu proses asynchronous di JavaScript sehingga kita perlu menggunakan salah satu diantara promise atau async/await.
- contoh request data dengan fetch() menggunakan promise:
  ```javascript
  fetch("https://jsonplaceholder.typicode.com/posts")
    .then(function (response) {
      return response.json();
    })
    .then(function (post) {
      console.log(post);
    });
  ```
- contoh request data dengan fetch() menggunakan async/await:
  ```javascript
  const tesFetchAsync = async () => {
    let response = await fetch("https://jsonplaceholder.typicode.com/posts");
    response = await response.json();
    console.log(response);
  };
  tesFetchAsync();
  ```
## JavaScript Intermediate - Asynchronous Async Await
- Async/await baru ada ketika update ES8  JavaScript dan dibangun menggunakan promise. Jadi sebenarnya async/await dan promise itu sama saja, namun hanya berbeda dari syntax dan cara penggunaannya.
- Ada 2 kata kunci yang memiliki pengertian sebagai berikut:
  - `async`, mengubah function synchronous menjadi asynchronous.
  - `await`, menunda eksekusi hingga proses asynchronous selesai.
- Sebuah async function bisa tidak berisi await sama sekali atau lebih dari satu await. Keyword await hanya bisa digunakan didalam async function, jika digunakan di luar async function maka akan terjadi error.
- await hanya bisa digunakan dalam async function dan await adalah keyword dalam async yang digunakan untuk menunda hingga proses asynchronous selesai.
-  contoh penggunaan dari async/await :
   ```javascript
   // Definisikan dahulu promise yang ingin digunakan
   let condition = true;
   let tesAsyncAwait = async (condition) => {
     if (condition) {
       return "Condition is fulfilled!";
     } else {
       throw "Condition is rejected!";
     }
   };

   // Membuat fungsi run menjadi asynchronous menggunakan async/await
   const run = async (condition) => {
     try {
       const message = await tesAsyncAwait(condition);
       console.log(message);  // Output: Condition is fulfilled!
       console.log("After condition is fulfilled"); // Output: After condition is fulfilled
     } catch (error) {
       console.log(error);
     }
   };

   run(true);
   ```
## Git & Github Lanjutan
- Branch merupakan cabang dari repository yang dapat digunakan saat kita akan menambahkan fitur baru atau memperbaiki bug.
- Merge adalah suatu command dalam git untuk membuat branch yang bercabang menjadi satu kembali atau dengan kata lain mengintegrasikan kembali branch tersebut menjadi satu. 
- Github Organization <br>
Git organization merupakan sebuah wadah yang disediakan oleh github untuk dapat melakukan kolaborasi. Untuk membuat github organization dapat dilakukan dengan cara-cara berikut :
  - Klik tombol (+) yang ada di kanan atas pada halaman github. Nanti akan muncul sebuah dropdown
  - Dari dropdown tersebut klik tombol new organization.
  - Setelah itu, pilih opsi sesuai yang ingin dibuat.
  - Melakukan Set up your organisasi.
  ### Kolaborasi
  **Tahapan yg dilakukan Team Lead :**
- Buat organization
  1. Team lead membuat organization
  2. Invite anggota tim dan jadikan owner
- Buat Repo di organization
  1. Team lead buat repo untuk project yg akan di buat
  2. Repo dibuat public, dan ceklis README
  3. Buat branch bernama dev
- Mengecek pull request
  1. Setiap ada pull request, team lead akan mengeceknya
  2. Jika pull request belum sesuai, bisa dikasih komen atau beri kabar anggota yg melakukan pull request tersebut
  3. Jika sudah sesuai, lakukan merge
- Jika mengikuti -> Hacktoberfest
  1. Repo diberi label hacktoberfest
  2. Setiap pull request yg di acc, diberi label hacktoberfest-accepted
  ##### **Tahapan yg dilakukan semua anggota:**
  1. masing-masing anggota lakukan clone pada repo yg sudah dibuat (1x aja)
  2. Bagi tugas pada masing-masing anggota kelompok
  3. Sebelum ngoding, lakukan git pulluntuk update kode terbaru
  4. Anggota membuat branch dari dev
  5. Lakukan pengerjaan di dlm branch yg sudah dibuat
  6. Jika fitur sudah selesai/butuh code dari dev, lakukan commit seperti biasa
  7. Sebelum push, lakukan git merge devuntuk menhindari conflict di github
  8. Jika ada conflict, bereskan semuanya
  9. Jika sudah aman, commit lalu push branch ke github
  10. Lakukan pull request untuk merge ke branch dev
  11. Tunggu pull request di acc oleh team lead

## Responsive Web Design
- Responsive Web Desin (RWB) adalah bertujuan membuat desain website yang dapat diakses dalam device apapun.
- Chrome Dev Tools merupakan tools pada google chrome yang digunakan sebagai tools Responsive Web Design. Untuk mengakses Chrome Dev Tools menggunakan: 
  > Ctrl + Shift + J
- Secara umum viewport adalah daerah pada layar yang menampilkan suatu konten.
- Dalam menggunakan Responsive Web Design pada bagian HTML perlu ditambahkan viewport pada bagian head agar tampilan website dapat menyesuaikan dengan berbagai device.
  ```html
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  ```
- Penjelasan kode di atas:
  - ``width=device-width`` memberitahu browser untuk mengikuti lebar layar dari perangkatnya. Sebab lebar layar tiap perangkat berbeda-beda.
  - ``initial-scale=1.0`` memberitahu browser tingkat pembesaran (zoom level) dari halaman itu.
- Media Query digunakan untuk mengatur lebar suatu element dan/atau memberikan style lain yang berbeda-beda sesuai dengan ukuran dari browser.
- Jenis media query
  - Media query untuk responsive web design umumnya hanya menggunakan 2 jenis media query.
  - Keduanya yaitu min-width dan max-width.
- Ada 2 cara/pattern dalam menggunakan media query:
  1. Membuat files css berbeda untuk masing - masing device
  2. Menggabungkan 1 files CSS untuk setting styling berbagai device 
- Contoh penerapan media query 
  `` @media screen and (max-width: 600px)``
- Breakpoint adalah perubahan yang terjadi pada tampilan tampilan saat berganti device atau ukuran width.
- Terdapat 3 jenis breakpoint yaitu desktop, ipad/tablet, dan mobile phone
- Penggunaan breakpoint pada media query dapat dilakukan dengan membuat range ukuran sesuai dengan tampilan device yang ingin dibuat.
- Contoh breakpoint dapat ditulis seperti ini
  ```css
  @media screen and (min-width: 500px) and (max-width: 700px) {
  body {
    background-color: yellow; 
    }
   }
  ```
- Flexbox adalah cara untuk mengatur layout. Flexbox memudahkan para programmer untuk mengatur layout, posisi, dan ukuran dari tiap element di dalamnya.
- Flexbox properties :
  - Flex direction : menetapkan sumbu utama item, sehingga menentukan arah item fleksibel ditempatkan di wadah fleksibel. 
    - Row : Kiri ke kanan
    - Row-Reverse : Kanan ke kiri
    - Column : Atas ke bawah
    - Column-Reverse : Bawah ke atas
  - Flex Wrap : Secara default, semua item pada flexbox akan mencoba berada dalam satu baris. Maka dengan flex wrap kita dapat mengubah hal tersebut.
    - nowrap : semua item flex akan berada dalam satu baris
    - wrap : item fkex akan membungkus ke beberapa baris, dari atas ke bawah.
    - wrap-reverse :item flex akan membungkus beberapa baris dari bawah ke atas.
  - Flex flow : cara singkat untuk properti flex-direction dan flex-wrap, yang bersama-sama menentukan sumbu utama dan sumbu silang container flex. Nilai default adalah baris nowrap.
  - Align items : digunakan untuk mengatur align dari item child secara vertikal atau cross axis.
- Grid merupakan sistem tata letak berbasis dua dimensi.
- Pada Grid ada 2 jenis yaitu grid container dan grid item.

## Bootstrap
- Awalnya bootstrap dibuat dan dikembangkan oleh Developer Twitter yaitu Mark Otto dan Jacob Thornton. Sebelum dikenal dengan nama Bootstrap seperti sekarang, awalnya bernama Blueprint Twitter.
- Bootstrap adalah kerangka kerja CSS yang sumber terbuka dan bebas untuk merancang situs web dan aplikasi web. Kerangka kerja ini berisi templat desain berbasis HTML dan CSS untuk tipografi, formulir, tombol, navigasi, dan komponen antarmuka lainnya, serta juga ekstensi opsional JavaScript.
- Komponen utama bootstrap :
  - bootstrap.css
  - bootstrap.js
- Cara konfigurasi bootstrap :
  - Kita dapat menggunakan bootstrap dengan beberapa cara yaitu didownload secara offline dan menggunakan CDN Link. Disini saya menggunakan CDN Link.
    ```html
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi" crossorigin="anonymous">
    
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3" crossorigin="anonymous"></script>
    ```
- Komponen Bootstrap sebagian besar dibangun dengan base-modifier nomenclature.Contohnya mengelompokkan beberapa properti kedalam kelas dasar seperti .btn, seperti .btn-primary or .btn-success.
- Layout pada boostrap :
<br>Breakpoints merupakan suatu cara yang dilakukan untuk membuat desain responsif dengan mengontrol kapan tata letak yang disesuaikan dengan ukuran perangkat tertentu.
    - Breakpoints pada bootstrap ada 6 yaitu xs, sm, md, lg, xl dan xxl.
    - Setiap breakpoint dipilih untuk menampung container yang lebarnya 12 dengan sehingga tersusun rapi. Breakpoint juga mewakili subset ukuran perangkat umum dan dimensi area pandang.
 - Container adalah sebuah elemen yang dapat digunakan untuk membuat responsive web design. Container dapat digunakan untuk membuat responsive web design.
- Terdapat 3 container pada boostrap yaitu :
    - .container, yang menerapkan lebar maksimum pada setiap breakpoint responsif
    - .container-{breakpoint}, menerapkan lebar 100% sampai dengan breakpoint yang ditentukan.
    - .container-fluid, menerapkan 100% ukurannya dari breakpoints
 - Grid System pada bootstrap terdiri dari 12 kolom default.
 - Grid system pada bootstrap menggunakan container,baris dan kolom untuk menata dan menyelaraskan konten,yang dibangun menggunakan flexbox dan itu sudah responsive.
  - contoh penggunaan grid system
    ```html 
    <div class="container text-center">
      <div class="row">
        <div class="col">
         Column
        </div>
        <div class="col">
         Column
        </div>
        <div class="col">
         Column
        </div>
      </div>
    </div>
    ```
    <br>Contoh di atas membuat tiga kolom dengan lebar yang sama di semua perangkat dan area pandang / viewport menggunakan kelas grid yang telah ditentukan sebelumnya. Kolom tersebut dipusatkan di halaman dengan induk .container.
- Grid system bootstrap :
  - .col-xs memiliki dimensi <576px
  - .col-sm memiliki dimensi >= 576px
  - .col-md memiliki dimensi >= 768px
  - .col-lg memiliki dimensi >= 992px
  - .col-xl memiliki dimensi >= 1200px
  - .col-xxl memiliki dimensi >= 1400px
