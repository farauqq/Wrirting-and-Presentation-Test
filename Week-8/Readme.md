# Writing Test Week 8
### React Context <br>
Context menyediakan cara untuk membagi data yang dapat diakses oleh banyak komponen tanpa harus mengirimkan props secara manual ke setiap level. Context dapat digunakan untuk mengatasi masalah yang sering terjadi dalam React, seperti prop drilling dan membagi state yang berbeda antar komponen.
- Sebelum Menggunakan Context
  - Context terutama digunakan ketika beberapa data harus dapat diakses oleh banyak komponen pada tingkat bersarang yang berbeda. Gunakan dengan hemat karena membuat penggunaan kembali komponen menjadi lebih sulit.
  - Jika Anda hanya ingin menghindari mengoper beberapa props melalui banyak tingkatan, komposisi komponen seringkali menjadi solusi yang lebih sederhana daripada context.
- Kapan Menggunakan Context
  - Context dirancang untuk berbagi data yang dapat dianggap “global” untuk diagram komponen React, seperti pengguna terotentikasi saat ini, tema, atau bahasa yang disukai.
- Membuat Context <br>
Context dapat dibuat dengan menggunakan `React.createContext()`. Context ini
dapat digunakan untuk menyimpan data yang dapat diakses oleh komponen-komponen
yang berada di dalamnya.
  ```javascript
  import React from "react";
  
  const UserContext = React.createContext();
  
  export default UserContext;
  ```
### React Testing <br>
React Testing Library menyediakan cara untuk melakukan testing pada komponen React. React Testing Library dapat digunakan untuk melakukan testing pada komponen React tanpa harus menguji implementasi detail dari komponen tersebut. React Testing Library dapat digunakan untuk melakukan testing pada komponen React tanpa harus menguji implementasi detail dari komponen tersebut.
- Install React Testing Library
npm install --save-dev @testing-library/react
- Step dari sebuah Testing
  - Assert, Hasil yg diharapkan: Langkah-langkah tindakan harus menimbulkan semacam tanggapan. Terkadang, pernyataan sesederhana memeriksa nilai numerik atau string. Di lain waktu, mungkin memerlukan pemeriksaan beberapa aspek sistem. Pernyataan pada akhirnya akan menentukan apakah tes lulus atau gagal.
  - Arrange, Input dan Target : Mengatur langkah-langkah harus mengatur kasus uji. Apakah tes memerlukan objek atau pengaturan khusus, apakah perlu menyiapkan database dan apakah perlu masuk ke aplikasi web
  - Act, Berdasarkan Perilaku Target: Langkah-langkah tindakan harus mencakup hal utama yang akan diuji. Ini bisa berupa memanggil fungsi atau metode, memanggil REST API, atau berinteraksi dengan halaman web. Juga agar tindakan tetap fokus pada perilaku target.
- Alasan mengapa Menggunakan Testing:
  1. Aplikasi bebas dari error dan bug
  2. Aplikasi berjalan sesuai dengan ekspektasi
  3. Meningkatkan kualitas dari sebuah software dan kepuasan pengguna
- Testing dibagi menjadi 2:
  - Manual Testing <br>
  Manual Testing yaitu testing yang dilakukan dengan melakukan pengecekan terhadap masing-masing fitur yang telah dibuat. Misalnya telah membuat fitur login, di cek apakah fitur login tersebut sudah jalan sesuai ekpektasi apa belum, apakah masih ada bug ketika user mengklik tombol loginnya, dll.
  - Automated Testing <br>
  Automation Testing yaitu testing yang dilakukan olah kode porgram yang telah kita buat, kode program tersebut nantinya akan mengecek tiap fitur yang telah dibuat. Automation testing sendiri ada 3 macam, diantaranya : <br>
    1. unit testing = testing yang dilakukan pada bagian paling terkecil, seperti function.
    2. integration = testing yang dilakukan dengan mengintegrasikan / menyambungkan dengan aplikasi / sistem lain, seperti database.
    3. end to end = testing yang dilakukan terhadap software mulai dari awal sampai akhir mencakup experience dari user. Testing ini merupakan testing yang membutuhkan banyak biaya karena bisa dibilang testing ini adalah testing yang kompleks / testing yang tidak bisa dilakukan oleh programmer sendiri, tidak seperti unit testing yang masih bisa dilakukan oleh programmer sendiri.
- Alasan menggunakan Automated Testing <br>
  1. Lebih reliable karena Manual Testing tetap berpotensi adanya kesalahan dan kekeliruan
  2. Lebih cepat dan efisien
  3. Mudah untuk dimaintain (Review, Edit, dan Add Collection of Tests)
- Dalam melakukan testing juga terdapat yang namanya TDD (Test Driven Development). Pada umumnya testing dilakukan setelah fitur selesai dibuat, proses ini terjadi pada development biasa. Sedangkan pada proses TDD, testing dilakukan lebih dulu sebelum membuat fitur. Dalam TDD, terdapat sebuah lifecycle diantaranya yaitu :
  - Red zone (Test Fails) = berisi sebuah ekspektasi (masih belum ada code program, hanya ekspektasi saja).
  - Green zone (Test Passess)= realasasi dari ekspektasi tersebut (proses pembuatan code program).
  - Blue zone (Refactor) = tahap efisiensi dari code program, seprti membuat codingan yang simple, mudah dimengerti, dan rapi. Intinya untuk membuat code yang telah dibuat sebelumnya agar lebih rapi & efisien.