# Writing and Presentation Test Week 2
## Javascript Dasar - Scope and Function
-  **Scope** adalah konsep dalam flow data variabel. Menentukan suatu variabel bisa diakses pada scope tertentu atau tidak.
-  Scope terdiri dari 2 macam yaitu:
   1. Global Scope
   2. Local Scope
-  Global scope <br>
   Global scope berarti variabel yang kita buat dapat diakses dimanapun dalam suatu file.Agar menjadi Global Scope, suatu variabel harus dideklarasikan diluar Blocks.<br>
  contoh:
   ```javascript
   let myName = 'Farauq';
   function greeting(){
      return myName; 
   }
   console.log(myName);
   ```
-  Local Scope<br>
   Local scope berarti kita mendeklarasikan variabel didalam blocks seperti function, conditional, dan looping.Maka variabel hanya bisa diakses didalam blocks saja. Tidak bisa diakses diluar blocks.<br>
  contoh:
   ```javascript
   function greeting(){
      let myName = 'Farauq';
      return myName; 
   }
   console.log(greeting()) 
   console.log(myName); 
   ```
   #### Javascript Dasar - Function
- **Function** adalah sebuah blok kode dalam sebuah grup untuk menyelesaikan 1 task/1 fitur.
- Membuat function<br>
  contoh:
   ```javascript
   function greeting() {
      return 'Hello Skilvul' ;
   }; 
   ```
- Memanggil Function <br>
  contoh:
   ```javascript
   greeting()
   console.log(greeting()); 
   ```
- Parameter dan Argumen
  - Parameter Function<br>
   Dengan parameter, function dapat menerima sebuah inputan data dan menggunakannya untuk melakukan task/tugas.Saat membuat function/fitur, kita harus tahu data-data yang dibutuhkan. Misalnya saat membuat function penambahan 2 buah nilai. Data yang dibutuhkan adalah 2 buah nilai tersebut.
    ```javascript
    function penambahan(x,y){
       return x + y;
    }
    ```
  - Argumen Function<br>
  Argumen adalah nilai yang digunakan saat memanggil function. Jumlah argumen harus sama dengan jumlah parameternya. Jadi jika di function penambahan ada 2 parameter nilai saat membuat function. Saat memanggil function kita gunakan 2 buah nilai argumen.
    ```javascript
    function penambahan(x,y){
       return x + y;
    }
    console.log(penambahan(10,5))
    ```
  - Default Parameters<br>
    Default paramaters digunakan untuk memberikan nilai awal/default pada parameter function. Default parameters bisa digunakan jika kita ingin menjaga function agar tidak error saat dipanggil tanpa argumen
    ```javascript
    function greetOnWebsite(name = 'Stranger'){
       return 'Hello ' + name;
    }
    console.log(greetOnWebsite('Maulana')) // output: 'Hello Maulana'
    console.log(greetOnWebsite()); // output: 'Hello Stranger'
    ```
- Function Helper<br>
    Kita bisa menggunakan function yang sudah dibuat pada function lain.<br>
contoh:
    ```javascript
    function multiplyByNineFifths(number) {
       return number * (9/5);
    };
    function getFahrenheit(celsius) {
       return multiplyByNineFifths(celsius) + 32;
    };
    getFahrenheit(15); // Returns 59
    ```
- Arrow function<br>
    Arrow function adalah cara lain menuliskan function. Ini adalah fitur terbaru yang ada pada ES6 (Javascript Version)
    ```javascript
    const greeting = () => {
      return 'Hello Skilvul'
    };

    const penambahan = (x, y) => {
      return x + y;
    };
    ```
- Short Syntax Function
  - Single-Line Block
    ```javascript
    const sumNumbers = number => number + number;
    ```
  - Multi-Line Block
    ```javascript
    const sumNumbers = number => {
       const sum = number + number;
       return sum;
    };
    ```
## Javascript Dasar - Data Type Built-in - Prototype and Method
- Tipe Data (Data Types) adalah klasifikasi yang kita berikan untuk berbagai macam data yang digunakan dalam programming.
- Secara umum tipe data terbagi menjadi 2:
  - Tipe data primitive adalah tipe data yang hanya dipakai untuk menyimpan data
  - Tipe data non primitive adalah tipe data yang selain dipakai untuk menyimpan data, tetapi juga mempunyai metode bawaan (built-in method) untuk dilakukan modifikasi dan operasi oleh programmer
- Data Primitive
1. **string** - Tipe data string adalah grup karakter yang ada pada keyboard laptop/PC kita yaitu letters (huruf), number (angka), spaces (spasi), symbol, dan lainnya. Harus diawali dan diakhiri dengan single quotes ‘ … ‘ ataupun double quotes “ … “.
   - Properties
     1. Constructor digunakan untuk mengembalikan fungsi yang dibuat string prototipe objek
     2. Length digunakan untuk mengembalikan panjang string JavaScript
        ```javascript
        const str = 'Farauq';
        console.log(str.length); // Output: 6
        ```
     3. Prototype digunakan untuk menambah metode dan properti ke dalam sebuah objek
        ```javascript
        String.prototype.reverse = function(){ 
          let s = " "    
          for (let i = String(this).length-1; i >= 0; i-- ){ 
            s = s + String(this)[i]
          } 
          return s 
        }
        console.log("Selamat Pagi".reverse()) // igaP tamaleS
        ```
   - Method
      1. toUpperCase() digunakan untuk Ubah string menjadi huruf besar
         ```javascript
         const str = 'msib';
         console.log(str.toUpperCase()); //Output: MSIB
     2. toLowerCase() digunakan untuk Ubah string menjadi huruf kecil
         ```javascript
         const str = 'Msib';
         console.log(str.toLowerCase()); //Output: msib
         ```
     3. charAt() digunakan untuk mengembalikan karakter pada index yang spesifik (posisi)
        ```javascript
        let sayur = 'Tomat';
        console.log(sayur.charAt(2)); //Output : m
        ```
     
2. **number** - Tipe data number adalah tipe data yang mengandung semua angka termasuk angka desimal.
   ```javascript
   const a = 11;
   console.log(a); // 11
   console.log(typeof a); // number
   console.log(a instanceof Number); // false    
    ```
     - Methods
        1. isNan() digunakan untuk mengecek apakah ini bukan angka. Mengembalikan nilai Boolean, true jika nilai yang diuji NaN(bukan angka), false jika angka
           ``` javascript
           isNan("farauq") // true
           isNan(12345) // false
           ```
        2. isInteger() digunakan untuk mengecek apakah value adalah sebuah integer.
           ```javascript
           Number.isInteger(11) // true
           Number.isInteger(11.30) // false
           ```
        3. toString() digunakan untuk mengubah angka menjadi string
           ```javascript
           let angka = 11
           angka.toString() //Output: '11'
           ```
        3. toFixed() digunakan untuk menentukan jumlah angka dibelakang tanda koma. Return nilainya berupa string
           ```javascript
           let phi = 3.14159265
           phi.toFixed() //Output: '3'
           phi.toFixed(1) //Output: '3.1'
           phi.toFixed(2) //Output: '3.14'
           ```
 - Data Non-Primitive
  1. Object
  2. Array
  3. Function
   #### Math
<br> Math object adalah object yang berisi method-method untuk melakukan operasi matematika
<br> contoh :
```javascript
Math.pi //Output: 3.1415
Math.LOG2E //Output: 1.4426
Math.sqrt2 //Output: 1.4426 {menghitung akar dua}
```
   - Methods Math
   1. Math.abs() digunakan untuk mengembalikan nilai negatif menjadi nilai positif
      ```javascript
      Math.abs(-11) //Output: 11    
      ```
   2. Math.pow() digunakan untuk menghitung pangkat
      ``` javascript
      Math.pow(8, 2) //Output: 64
      ```
   3. Math.sqrt() digunakan untuk menghitung akar
      ``` javascript
      Math.sqrt(64) //Output: 8
      ```
   4. Math.round() digunakan untuk membulatkan angka
      ``` javascript
      Math.round(123.456) //Output: 123
      ```
      
## Javascript Dasar - DOM
- **DOM (Document Object Model)** adalah semua element HTM yang dimodelkan sebuah objek. Objek element HTML di HTML DOM juga mempunyai properti dan method atau yang lebih dikenal dengan istilah DOM Property dan DOM Method.
- DOM bukan bagian dari JavaScript, melainkan browser (Web API). Fungsinya untuk memanipulasi tampilan web agar website lebih dinamis dan interaktif.
- Mengakses Element HTML :
  - getElementById(id)<br>
    Kita bisa menggunakan getElementById untuk mengakses element HTML berdasarkan nilai id-nya.
    ``` javascript
    console.log(document.getElementByID("header))
    ```
  - getElementsByTagName(tag)<br>
    Untuk mengakses element-element HTML berdasarkan jenis tag-nya, kita bisa menggunakan getElementsByTagName
    ``` javascript
    let semuaTagH1 = document.getElementsByTagName("h1");
    ```
  - getElementsByClassName(className)<br>
    Untuk mengakses element-element HTML berdasarkan nilai attribute class-nya, kita bisa menggunakan getElementsByClassName.
    ``` javascript
    let semuaClassHeader = document.getElementsByClassName("header");
    ```
  - querySelectorAll(cssSelector)<br>
    Untuk mengakses element-element HTML berdasarkan CSS Selector-nya HTML, kita bisa menggunakan querySelectorAll.
    ``` javascript
    console.log(document.querySelector("#header "))
    ```
    ``` javascript
    console.log(document.querySelector(".text-color-blue"))
    ```
- Memanipulasi Element HTML
   - Mencari Element HTML
      ``` javascript
      let header = document.getElementById("heading"); 
      ```
  - Mengubah Konten Element<br>
    Element.textContent dapat kita gunakan untuk mengubah teks di dalam sebuah element
    ```  javascript
    <h1 id="heading"></h1>
    document.getElementById("heading").textContent = "Teks Heading" 
    ```
     Element.innerHTML dapat kita gunakan untuk mengubah konten HTML di dalam sebuah element.

    ``` javascript
    <ul id= "list"></ul>
    document.getElementById("list").innerHTML = "<li>item1</li> <li>item2</li>"
    ```
- Membuat Element HTML<br>
  Contoh :
  ``` javascript
  <div id ="header"></div>

  //membuat element heading
  const heading = dosument.createElement("h1)
  heading.textContent = "Ini Heading"

  document.getElemntByID("header").appendChild(heading)
  ```
- DOM Events adalah cara untuk menangani event pada element HTML
- Berbagai HTML DOM Event:
  - Click
  - Change
  - Scroll
  - Submit
  - Hover
  - Focus
  - Blur
- Menangkap Interaksi User
  - Element.addEventListener("event)
  - Element.onevent
- EventListener <br>
  Dengan cara Element.addEventListener(“event”)
  - Bisa dihilangkan
  - Bisa ada beberapa event listener yang sama untuk 1 element
  - Memiliki argument tambahan {options}
- Contoh EventListener : <br>
    EventListener - Click <br>
    Misalkan kita mempunyai element `` <input id="user-input"/> `` `` <button id="alert-button">show</button> ``
    ``` javascript
     // cari dulu kedua element tersebut berdasarkan id-nya

    const input = document.getElementById(“user-input”)
    const button = document.getElementById(“alert-button”)

    // baru tambahkan event listener
    button.addEventListener(“click”, function() {
	    alert(input.value)
    })
    ```
- EventListener - Blur <br>
  “Blur”, lawan dari “focus”, adalah event di mana sebuah element kehilangan fokus dari user (misal user klk mouse di luar element tersebut atau user klik tab untuk berpindah element)
  Contoh EventListener - Blur <br />
  Misalkan kita ingin memvalidasi isi dari ``<input id = "username" />`` agar panjangnya minimal 8 karakter
  ``` javascript
  // cari dulu element tersebut berdasarkan id-nya

  const input = document.getElementById(“username”)

  // tambahkan event listener
  input.addEventListener(“blur”, () => {
      if(input.value.length < 8) alert(“Panjang username minimal 8”)
    })
  ```
- EventListener - Form Submission <br>
  Contoh EvenListener - Form Submission <br />
  Misalkan kita mempunyai element beberapa input dalam sebuah form `` <input name="email"/> `` dan ``<input type="password" name="password"/>`` <br />
  Untuk mendapatkan isi dari kedua inputan tersebut terdapat 2 cara :
  1. Memasang event listener di kedua input dan tombol submit, lalu saat tombol diklik, baca value dari kedua input tersebut
  2. Memasang event listener di form, lalu gunakan FormData untuk menggambil data dari masing-masing input
  ``` javascript
  const form = document.getElementById("form")

  form.addEventListener("submit", function(event)){
      event.preventDefault()

      const formData = new FormData(form)
      const values = Object.fromEntries(formData) {   // {email: ....}
  })
  ```