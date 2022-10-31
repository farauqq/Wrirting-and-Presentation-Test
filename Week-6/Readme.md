# Writing Test Week 6
## React Js
#### React Js Dasar - Introduction React JS
- React JS adalah framework view library Javascript untuk membuat tampilan (user interface) pada website. React Js dibuat oleh Tim Engineer Facebook menggunakan React Js pada sisi front-end.
- Kenapa menggunakan React Js? 
  1. React Js is Fast.<br>
     React Js membuat aplikasi front-end menjadi lebih cepat walaupun harus menghandle berbagai data.
  2. React Js is Modular.<br>
     Kita dapat menerapkan konsep Modular javascript pada React Js. React Js membagi 1 tampilan pada website menjadi komponen - komponen kecil.
  3. React JS is Scalable.<br>
     React JS dapat digunakan pada aplikasi berskala kecil hingga besar dan kompleks.
  4. React is Popular.<br>
    Komunitas React JS diseluruh dunia sangat besar. Kebanyakan perusahaan teknologi pun sudah menggunakan React JS.
- Instalasi React Js
  - Step 1 - Install Node Js, untuk melihat versi Node Js yang terinstall buka terminal atau command prompt (cmd) kemudian ketik perintah node -v.
  - Step 2 - Inisalisasi Proyek <br>
    - Buat folder atau siapkan folder yang akan kita install react.
    - Kemudian buka terminal dan ketikan perintah `npx create-react-app (my-app / nama-projeknya)`, tunggu hingga proses instalasi selesai.
    - Apabila sudah selesai terinstall akan muncul Happy Hacking pada line di terminal atau command prompt (cmd)
  - Step 3 - Menjalankan Proyek <br>
    Buka folder proyek yang telah dibuat, kemudian jalankan terminal / cmd ketikan perintah `npm start`.
- JSX adalah syntax extention for Javascript. JSX dikembangkan untuk digunakan pada React Js. Dengan JSX kita dapat menggunakan HTML didalam file extention Javascript (.js).<br>
Contoh JSX: 
  ```javascript
  import React from "react";

  const HelloWorld = () => {
    return (
      <>
        <h1> Latihan React Js </h1>
        <p> JSX adalah syntax extention for Javascript. </p>
      </>
    );
  };
  
  export default HelloWorld;
  ```
- JSX Rules
  1. Setiap JSX hanya bisa memiliki 1 parent element.
  2. Memiliki DOM manipulation
  3. Atribut class di tag HTML harus menggunakan className
  4. Menggunakan curly braces untuk mengakses variabel JSX
- Virtual DOM adalah duplikasi dari real DOM yang sebenarnya. Dengan DOM kita dapat berinteraksi seperti mengupdate data di web page.
#### Component
- Component adalah salah satu core dalam React Js. Component membagi UI dalam satuan kecil artinya dalam 1 page ada beberapa component yang bisa dibuat.
- Ada 2 cara membuat component :
  1. Menggunakan Function
  ```javascript
  // Cara 1
  import React from "react";

  function App() {
    return (
      <div>
        <h1> Function Component Cara 1 </h1>
      </div>
    );
  };

  export default App;
  ```
  ```javascript
  // Cara 2
  import React from "react";

  const App = () => {
    return (
      <div>
        <h1> Function Component Cara 2 </h1>
      </div>
    );
  };

  export default App;
  ```
  2. Menggunkaan Class
  ```javascript
  import React from "react";

  class App extends React.Component {
    render() {
      return (
        <div>
           <h1> Class Component </h1>
        </div>
      )
    };
  };

  export default App;
  ```
#### State & Props
- State adalah data private sebuah component. Data ini hanya tersedia untuk component tersebut dan tidak bisa di akses dari component lain. Component dapat merubah statenya sendiri.
- Props singkatan dari Property. Prop umumnya digunakan untuk komunikasi data component dari parent komponent ke child component.Prop itu read-only function ini hanya bisa membaca parameter props tetapi tidak bisa merubahnya.
#### Lifecycle
- Lifecycle jika dianalogikan bisa dianggap seperti lingkaran kehidupan selama 24jam mulai dari bangun tidur hhingga tidur lagi.
- Lifecycle pada React adalah aktifitas method yang dilakukan oleh React ketika aplikasi dijalankan.
- Setiap React component akan melewati 3 fase,yakni:
  1. Fase Mounting adalah fase ketika components di buat atau pertama kali di render ke DOM. Pada fase ini ada tiga methods yang akan di eksekusi yaitu componentWillMount, render, dan componentDidMount.
  2. Fase Updating adalah fase ketika sebuah component akan di render ulang, biasanya ini terjadi ketika ada perubahan pada state atau props yang mengakibatkan perubahan DOM.adalah fase ketika sebuah component akan di render ulang, biasanya ini terjadi ketika ada perubahan pada state atau props yang mengakibatkan perubahan DOM.
  3. Fase Unmounting adalah fase ketika component di hapus dari DOM. Pada fase ini hanya ada satu method yang akan di eksekusi yaitu componentWillUnmount.
#### Styling React Js
- Styling pada React.js dapat dilakukan dengan menggunakan beberapa cara yakni: Inline styling, CSS file, CSS Module dan Styled Components.<br>
Contoh Inline Styling:
  ```javascript
  import React from 'react';

  const App = () => {
    return (
      <>
        <h1 style={{backgroundColor: "lightblue"}}>Hello World!</h1>
        <p style={{color: "grey"}}>My Name is Farauq<p>
      </>
    );
  }
  ```
#### React Js Lanjutan - Hooks
- Hooks merupakan fitur baru yang dikenalkan di React Js pada tahun 2018.
- Hooks digunakan untuk memudahkan penggunaan functinal components agar bisa menggunakan state dan lifecycle lainnya. Sebelumnya state (setState) dan lifecycle (componentDidMount, componentDidUpdate) hanya bisa digunakan di class component, namun dengan hooks, kita bisa menggunakannya di functional components. <br>
Contoh Hooks useState:
  ```javascript
  import React, { useState } from "react";

  const App = () => {
    const [name, setName] = useState("Farauq");

    return (
      <div>
        <h1>Hello, {name}</h1>
      </div>
    );
  };

  export default App;
  ```