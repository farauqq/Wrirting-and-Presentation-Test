# Writing and Presentation Test Week 3
## JS Intermediate - Array dan Multidimensional Array
-  **Array** adalah tipe data list order yang dapat menyimpan tipe data apapun di dalamnya. Array dapat menyimpan tipe data String, Number, Boolean, dan lainnya.<br>
  contoh:
   ```javascript
   let learningTrack = ['Front-End Web Dev', 'Back-End Web Dev', 'Game Dev'];
   console.log(learningTrack);
   ```
   ```javascript
   // Menyimpan banyak tipe data (String, Number, dan Boolean)
   let randomData = ['Ini string', 11, true];
   console.log(randomData);
   }
   console.log(greeting()) 
   console.log(myName); 
   ```
- Array didefinisikan menggunakan square brackets ``[]``
- Mengakses/Memanggil Array pada javascript dihitung dari index data ke-0.<br />Data pertama adalah index ke-0.
   ```javascript
   let learningTrack = ['Front-End Web Dev', 'Back-End Web Dev', 'Game Dev'];
   console.log(learningTrack[0]);  //output: Front-End Web Dev
   ```
- Update Array
   ```javascript
   let learningTrack = ['Front-End Web Dev', 'Back-End Web Dev', 'Game Dev'];
   learningTrack[2] = 'UI/UX Design';
   console.log(learningTrack);
   // output: ['Front-End Web Dev', 'Back-End Web Dev', 'UI/UX Design'];
   ```
- Const in Array
  - Apabila menggunakan let, array dapat diubah dengan nilai yang baru
  - Const tidak dapat melakukan update data. Namun dapat melakukan update konten nilai di dalam array
  - Tidak dapat mengubah array dengan array baru jika menggunakan const
  ``` 
  const cars = ['tesla', 'bmw', 'nissan'];
  cars[2] = ['mercy'];
  console.log(cars)// output : ['tesla','bmw','mercy']
  ```
- Array Properties, array memiliki 5 properti yang sering digunakan yaitu constructor, length, index, input, dan prototype.
- .length yaitu mengembalikan nilai dari jumlah panjang data suatu array
   ```javascript
   let learningTrack = ['Front-End Web Dev', 'Back-End Web Dev', 'Game Dev'];
   console.log(learningTrack.lenght); // output: 3
   ```
- Array Method<br /> Array memiliki method atau biasa disebut built-in methods.
- Contoh array built in method :
    - .push adalah method untuk menambahkan item array pada urutan yang paling akhir  
      ```
      let cars = ['tesla', 'bmw', 'mercy'];
      cars.push('hyundai')
      console.log(cars) // output:['tesla','bmw','mercy','hyundai']
      ```
    - .pop adalah method yang menghapus item array index terakhir
      ``` 
      let cars = ['tesla', 'bmw', 'mercy'];
      cars.pop()
      console.log(cars) // output: ['tesla','mercy']
      ```
    - .shift adalah method untuk menghapus item array pada index pertama 
      ``` 
      let cars = ['tesla', 'bmw', 'mercy'];
      cars.shift()
      console.log(cars) // output: ['bmw', 'mercy']
      ```
    - .unshift adalah method untuk menambahkan array pada index pertama 
      ``` 
      let cars = ['tesla', 'bmw', 'mercy'];
      cars.unshift('ferrari')
      console.log(cars) // output:['ferrari','tesla','bmw','mercy']
      ```
     - .sort adalah method untuk mengurutkan array secara ascending atau descending
       ``` 
       const numbers = [1,5,6,7,4];
       numbers.sort();
       console.log(numbers) // output : [1,4,5,6,7]
       ```
- Looping pada Array<br /> Built in methods untuk melakukan looping pada array ada .map dan .forEach
    - .forEach adalah method untuk melakukan looping pada setiap elemen array 
      ```
      const cars = ['tesla', 'bmw', 'mercy'];
      cars.forEach(element => {
      console.log(element);
      }); // output: 'tesla', 'bmw', 'mercy'
      ```
    - .map adalah method untuk melakukan perulangan dengan membuat array baru
      ```
      let arr = [1,2,3,4,5];
    
      let doubled = arr.map(num => {
          return num * 2;
      });
      console.log(doubled);  // output: [2,4,6,8,10]
      ```
   #### Multidimensional Array
- Multidimensional Array bisa dianalogikan dengan array of array. Ada array didalam array.
    ```
    let inventory = [
        ['Kaos Polos' , 10],
        ['Jaket' , 5],
        ['Topi' , 12],
        ['Celana' , 4],
    ];
    console.log(inventory);
    ```
- Mengakses index multidimensional array
     ```
    let inventory = [
        ['Kaos Polos' , 10],
        ['Jaket' , 5],
        ['Topi' , 12],
        ['Celana' , 4],
    ];
    console.log(inventory[1][0]);
    ```
- Penggunaan built in method pada multidimensional array
    ```
    let inventory = [
        ['Kaos Polos' , 10],
        ['Jaket' , 5],
        ['Topi' , 12],
        ['Celana' , 4],
    ];
    inventory.push(['Hoodie', 2]);
    console.log(inventory);
    ```
- Operation using map in multidimensional array
    ```
    let inventory = [
        ['Kaos Polos' , 10],
        ['Jaket' , 5],
        ['Topi' , 12],
        ['Celana' , 4],
    ];
    inventory.map(dataInventory => {
        let terjual = 100 - dataInventory[1];
        dataInventory[2] = terjual;
    });
    console.table(inventory);
    ```
- Looping for Multidimensional array
    ```
    let inventory = [
        ['Kaos Polos' , 10],
        ['Jaket' , 5],
        ['Topi' , 12],
        ['Celana' , 4],
    ];
    inventory.forEach((baris) => {
        baris.forEach((column) => {
            console.table(column);
        });
    });
    ```
## JS Intermediate - Object
- Pada programming, object adalah sebuah tipe data pada variabel yang menyimpan properti dan fungsi (method)
- Properti adalah data lengkap dari sebuah object.
- Method adalah action dari sebuah object. Apa saja yang dapat dilakukan dari suatu object.
- Membuat sebuah object
   ```javascript
    let person = {
        name : 'Farauq',
        age : 20,
        isVerified: true
    }
   ```
- Mengakses Object dan Property Object
    ```javascript
    let person = {
        name : 'Farauq',
        age : 20,
        isVerified: true
    }
    console.log(person);
   ```
- Mengakses Property Object
    ```javascript
    let person = {
        name : 'Farauq',
        age : 20,
        isVerified: true
    }
    console.log(person.name);
   ```
- Bracket Notation digunakan saat memanggil properti dari sebuah object.
    ```javascript
    let person = {
        name : 'Farauq',
        age : 20,
        'current address': 'Kudus','Jateng'
    }
    console.log(person['name'])
    console.log(person['current address'])
    ```
- Update Object
  - Object dapat mengupdate value dari key yang sudah tersedia
  - Object dapat menambahkan key dan value baru
    ```javascript
    let person = {
        name : 'Farauq',
        age : 20,
        isVerified: true
    }
    person.age = 21;
    person.addres = 'Kudus, Jateng';
    console.log(person);
    ```
- Delete Object Property
    ```javascript
    let person = {
        name : 'Farauq',
        age : 20,
        isVerified: true
    }
    delete.person.age;
    console.log(person);
- Method disebut Jika value yang kita masukkan pada property berupa function.
- Nested Object adalah Object yang berasal dari turunan object lainnya.
- Passed by reference yakni mengubah data yang ada pada object melalui sebuah function dan memasukkan object sebagai parameter function.
- Looping Object, jika ingin menampilkan seluruh object properti. Bisa menggunakan looping. Sehingga tidak perlu mengakses secara manual memanggil setiap propertinya.
- Array of Object, berarti list/kumpulan/daftar object yang seragam. Dikatakan seragam karena objek yang berada dalam satu array pasti memiliki property yang sama. 
## JS Intermediate - Rekrusif dan Modules
- Recursive adalah function yang memanggil dirinya sendiri sampai kondisi tertentu.
- Struktur Rekrusif
  ```
  function Rekrusif(){
      // ...
      recrsive();
      // ...
  }
  ```
- Ciri dari rekursif:
  - Fungsi rekursif selalu memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti. Kondisi ini harus dapat dibuktikan akan tercapai, karena jika tidak tercapai maka kita tidak dapat membuktikan bahwa fungsi akan berhenti, yang berarti algoritma kita tidak benar.
  - Fungsi rekursif selalu memanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya. Hal ini penting diingat, karena tujuan utama dari rekursif ialah memecahkan masalah dengan mengurangi masalah tersebut menjadi masalah-masalah kecil.
- Contoh kasus rekursif (Mencari hasil dari nilai pangkat dengan rekursif)
  ```
  function pow(x, n) {
      if (n = 1) {
          return x;
      } else {
          return x * pow(x, n - 1);
      }
  }
  console.log(pow(2, 3)); // output: 8
  ```
   #### Modules
- Modules adalah cara untuk memisahkan kode ke file yang berbeda. Keuntungan dari modules yaitu mudah untuk mengelola kode serta kode tidak menumpuk di dalam satu file. Terdapat 2 kata kunci pada modules yaitu export dan import. Contoh :
  ```
  // File Jepang.js
  export let motor = ["suzuki", "yamaha", "honda", "kawasaki"]
  
  let entertainment = ["anime", "manga", "wibu", "dorama"]
  export default entertainment
  
  export function sayHello() {
   console.log("hallooo")
  }
  
  import {apple} from './amerika.js';
   console.log(apple);
  
  // File Indonesia.js
  import {motor} from "./Jepang.js"
   console.log(motor);
   
  import Entertainment, { motor as motorJepang, sayHello  } from "./jepang.js"
  console.log(Entertainment);
  
  // File Amerika.js
  let apple = ["iphone", "macbook", "imac"]
    export {apple}
  
  Berdasarkan script diatas,
  - Indonesia hanya bisa import, karena dia file utama.
  - Jepang bisa melakukan import dan export.
  - Amerika hanya melakukan export.
  ```
## JavaScript Intermediate Web Storage
- Ada beberapa cara untuk menyimpan data pengguna seperti pencarian, artikel berita, dan lain-lain ke lokal (browser) menggunakan web storage seperti cookies, local storage, dan session storage. Data ini dimanfaatkan oleh situs web tersebut untuk merekam kebiasaan pengguna agar dapat memberikan rekomendasi sesuai preferensi si pengguna tersebut.
   #### Cookies
- Cookies adalah data kecil yang dikirim dari situs web dan disimpan di komputer kita oleh web browser saat kita menjelajah. Disebut data kecil karena maksimum data yang dapat disimpan dalam cookies adalah 4096 bytes (4 KB).
- Biasanya data yang disimpan di cookies adalah access token pengguna saat login atau data pencarian saat melakukan pencarian pada situs web tertentu. Hal ini yang biasanya dilakukan oleh situs pencarian untuk melacak pencarian kita dan menampilkan iklan yang berhubungan dengan pencarian kita sebelumnnya.
- Namun ada beberapa kekurangan yang perlu kita perhatikan mengenai cookies di antaranya:
  1. Setiap kita mengakses situs web, cookies juga kembali dikirim sehingga memperlambat aplikasi web kamu dengan mengirimkan data yang sama.
  2. Cookies disertakan pada setiap HTTP request, sehingga mengirimkan data yang tidak dienkripsi melalui internet, maka saat kita ingin menyimpan data dalam cookies kita harus mengenkripsinya terlebih dahulu.
  3. Cookies hanya dapat menyimpan data sebanyak 4KB.
  4. Lalu cookies juga memiliki tanggal kadaluarsa. Tanggal ini telah ditentukan sehingga web browser bisa menghapus cookies jika tanggal sudah kadaluarsa atau tidak dibutuhkan.
- Kita dapat memanfaatkan jenis web storage yang lain untuk mengatasi kekurangan yang dimiliki cookies.
   #### Local Storage & Session Storage
- Pernahkah kita saat melakukan pencarian pada sebuah situs lalu situs tersebut menampilkan riwayat pencarian kita? Iya, data pencarian tersebut disimpan ke dalam local storage untuk diolah menjadi riwayat pencarian. Itulah salah satu contoh penerapan dari local storage pada aplikasi web.
- Berbeda dengan local storage, walaupun masuk ke dalam web storage, data yang tersimpan pada session storage akan hilang ketika session dari sebuah laman berakhir.
- Karakteristik Local Storage:
  1. Menyimpan data tanpa tanggal kadaluarsa.
  2. Data tidak akan dihapus ketika web browser ditutup dan akan tersedia seterusnya selama kita tidak menghapus data local storage pada web browser.
  3. Dapat menyimpan data hingga 5MB.
  4. Hanya dapat menyimpan data string.
- Sedangkan Karakteristik Session Storage:
  1. Data yang disimpan pada session storage akan terus tersimpan selama browser terbuka dan tidak hilang jika laman di-reload.
  2. Membuka banyak tab/window dengan URL yang sama, akan menciptakan session storage yang berbeda di masing-masing tab/window.
  3. Menutup tab/window akan mengakhiri session dan menghapus data yang tersimpan di session storage pada tab/window tersebut.
  4. Data yang tersimpan dalam session storage harus berbentuk string.
  5. Hanya dapat menyimpan data sebanyak 5MB.
   #### Mengakses Local Storage & Session Storage
1. Local Storage
  - Menyimpan Data
  Untuk menyimpan data pada local storage, kita menggunakan method `setItem()` yang membutuhkan 2 parameter. Parameter pertama adalah key yang ingin kita simpan dan parameter kedua adalah data (value) dari key yang akan disimpan.
    ```javascript
    localStorage.setItem('key', value);
    ```
  - Mengambil Data
  Untuk mengambil data yang telah tersimpan pada local storage, kita dapat menggunakan method `getItem()` yang membutuhkan 1 parameter. Parameter tersebut adalah key dari data yang kita inginkan.
      ```javascript
      localStorage.getItem('key');
      ```
  - Menghapus Data
  Untuk menghapus data yang telah tersimpan pada local storage, kita dapat menggunakan method `removeItem()` yang membutuhkan 1 parameter. Parameter tersebut adalah key dari data yang ingin kita hapus.
    ```javascript
    // menghapus key tertentu
    localStorage.removeItem("key");

    // menghapus semua key
    localStorage.clear();
    ```
2. Session Storage
  - Menyimpan Data
  Sama dengan local storage, sintaks untuk menyimpan data pada session storage adalah sebagai berikut:
    ```javascript
    // menambah session storage
    sessionStorage.setItem('key', value);
    ```
  - Mengambil Data 
  Sama seperti local storage, cara mendapatkan data dari session storage juga menggunakan `getItem(),` seperti berikut ini:
    ```javascript
    // mendapatkan session storage
    sessionStorage.getItem('key');
    ```
  - Menghapus Data
  Syntax untuk menghapus data dari session storage ada 2, yaitu:
    ```javascript
    // menghapus session storage satu persatu berdasarkan key
    sessionStorage.removeItem('key');

    // menghapus seluruh session storage sekaligus
    sessionStorage.clear();
    ```
## JS Intermediate - Asynchronous
- Asynchronous yang biasa dikenal juga dengan sebutan non-blocking mengizinkan komputer kita untuk memproses perintah lain sambil menunggu suatu proses lain yang sedang berlangsung. Ini artinya kita bisa melakukan lebih dari 1 proses sekaligus (multi-thread). Eksekusi perintah dengan asynchronous tidak akan melakukan blocking atau menunggu perintah sebelumnya selesai. Jadi sambil menunggu kita bisa mengeksekusi perintah lain.
- Penggunaan asynchronous dapat dilakukan jika kita ingin mengambil data dari database
- Mengapa perlu menggunakan asynchronous? Asynchronous dibutuhkan ketika ada proses yangg membutuhkan waktu lama. Jadi kita bisa mengerjakan proses yg lain secara paralel.
- Ada beberapa cara untuk membuat proses asynchronous. 
  1. `setTimeout(function, milliseconds)` digunakan untuk simulasi pemanggilan kembali proses asynchronous yang sedang/sudah selesai dijalankan. Pemanggilan hanya dilakukan 1 kali.
  2. `setInterval(function, milliseconds)` digunakan untuk simulasi pemanggilan proses asynchronous yang sedang/sudah dijalankan dalam interval waktu tertentu. Pemanggilan dilakukan berkali-kali sesuai interval waktu yang ditentukan.
- Contoh asynchronous menggunakan `setTimeout()`:
  ```
  setTimeout(() => {
    console.log("Cuci baju"); // proses asynchronous
  }, 1000);
  console.log("Menyapu");
  console.log("Mengepel");
  console.log("Memasak");

  // 1000 ms = 1 second

  // Output:
  // Menyapu
  // Mengepel
  // Memasak
  // Cuci baju
  ```
- Contoh asynchronous menggunakan `setInterval()`:
  ```
  setInterval(() => {
    console.log("Cuci baju"); // proses asynchronous
  }, 3000);
  console.log("Menyapu");
  console.log("Mengepel");
  console.log("Memasak");

  // 3000 ms = 3 second

  // Output:
  // Menyapu
  // Mengepel
  // Memasak
  // Cuci baju (x time)

  // Cuci baju akan dijalankan setiap 3 detik sekali
  ```
- Callback adalah sebuah function, namun bedanya dengan function pada umumnya adalah pada cara eksekusinya. Jika function pada umumnya dieksekusi secara langsung, sedangkan callback dieksekusi di dalam function lain melalui parameter.
- Promise merupakan suatu object dan digunakan hanya untuk satu event dengan menyimpan hasil dari sebuah operasi asynchronous baik itu hasil yang diinginkan (resolved value) atau alasan kenapa operasi itu gagal (failure reason).
-  Async-Await merupakan fitur yang hadir sejak ES2017 bekerja dengan cara menunda eksekusi hingga proses asynchronous selesai.
- Fetch merupakan cara baru dalam melakukan network request yang memanfaatkan sebuah Promise dalam penggunaanya. Karen Fetch mengembalikan sebuah Promise maka respon handling yang digunakan adalah **then** jika promise mengembalikan resolve dan **catch** jika promise mengembalikan nilai reject.
    #### API dan HTTP Request
- Application Programming Interfaces (API) adalah konstruksi yang tersedia dalam bahasa pemrograman untuk memungkinkan pengembang membuat fungsionalitas yang kompleks dengan lebih mudah. Mereka mengabstraksikan kode yang lebih kompleks dari Anda, menyediakan beberapa sintaks yang lebih mudah untuk digunakan sebagai gantinya.
- HTTP merupakan singkatan dari Hypertext transfer protocol, di desain untuk memungkinkan komunikasi antar klien dan server. HTTP berfungsi sebagai protokol Request-Response antara klien dan server. 
- HTTP Request yaitu Keadaan dimana server membaca apa yang dikirimkan oleh client melalui aplikasi web server
- HTTP Method :
  - GET digunakan untuk meminta data dari sumber tertentu
  - POST digunakan untuk mengirim data ke server untuk membuat/memperbarui resource
  - PUT digunakan untuk mengirim data ke server untuk membuat/memperbarui resource.
  - DELETE digunakan untuk menghapus spesifiksi resource
