# Writing Test Week 7
### React Js Lanjutan - Prop Types
- PropTypes merupakan sebuah lib yang dapat membantu untuk memeriksa data props yang dikirim agar sesuai dengan ekspetasi. Apabila tidak sesuai, maka akan muncul pesan error.
- Install Prop Types<br>
  `npm install prop-types`
- Contoh penggunaan PropTypes:
    ```javascript
    // StudentInfo.jsx
    import PropTypes from "prop-types";
    
    const StudentInfo = ({name, age}) => {
        return (
          <>
            <h2>{name}</h2>
            <h2>{age + 2}</h2>
          </>
        );
    };
    
    StudentInfo.proptypes = {
        name: PropTypes.string,
        age: Proptypes.number,
    };
    export default StudentInfo;
    ```
    ```javascript
    // App.jsx
    import React from "react";
    import StudentInfo from "./components/StudentInfo"
    
    const App = () => {
        return (
          <>
            <StudentInfo name={"farauq"} age={18} />
          </>
        );
    };
    export default App;
    ```
### React Router 6
- React Router merupakan standar routing yang digunakan sebagai library React JS untuk mengarahkan website dari page satu ke page lainnya. React Router 6 adalah versi terbaru dari React Router.
- Instalasi React Router
  - Untuk menambahkan react router hal yang harus dilakukan adalah menginstall dependensinnya, menginstallnya bisa menggunakan:
  1. npm : `npm install react-router-dom@6`
  2. Yarn : `yarn add react-router-dom@6`
  3. pnpm : `pnpm add react-router-dom@6`
  - Setelah proyek diatur dan react-router diinstal, buka src/index.js di teks editor. Menambahkan import { BrowserRouter } from "react-router-dom"; kemudian bungkus app dalam BrowserRouter.<br>
  Konfigurasi Router: 
    ```javascript
    import * as React from "react";
    import * as ReactDOM from "react-dom";
    import { BrowserRouter } from "react-router-dom";
    import "./index.css";
    import App from "./App";
    import * as serviceWorker from "./serviceWorker";
    
    ReactDOM.render(
     <BrowserRouter>
      <App />
     </BrowserRouter>
    };
    ```
- Ada beberapa contoh jenis dari Route yaitu :
  - Nested Route
  - Dynamic Route
- Contoh Nested Route:
  ```javascript
  function App() {
  return (
    <Routes>
      <Route path="invoices" element={<Invoices />}>
        <Route path=":invoiceId" element={<Invoice />} />
        <Route path="sent" element={<SentInvoices />} />
      </Route>
    </Routes>
   );
  }
  ```
- Contoh Dynamic Route:
  ```javascript
  <Routes>
    <Route path="/" element={<Home />} />
    <Route path="/books" element={<BookList />} />
    <Route path="/books/:id" element={<Book />} />
  </Routes>
  ```
### State Management - React Redux
- Redux adalah sebuah aplikasi state management. State management adalah cara untuk memfasilitasi komunikasi dan berbagai data lintas komponen.
- Intalasi Redux<br>
Untuk menambahkan redux  hal yang harus dilakukan adalah menginstall dependensinnya: `npm install redux react-redux`
- Ada 3 poin penting dalam redux :
  - Store digunakan untuk menyimpan dan mensuplai data ke UI lain atau yang membutuhkan.
    ```
    import { createStore } from 'redux';
    import todoReducer from './reducers';

    const store = createStore(todoReducer);
    ```
  - Action merupakan fingsi yang dipanggil oleh UI.
     ```javascript
    export function addTodo({ task }) {
    return {
      type: 'ADD_TODO',
      payload: {
        task,
        completed: false
      },
    }
    }

    // example returned value:
    // {
    //   type: 'ADD_TODO',
    //   todo: { task: '🛒 get some milk', completed: false },
    // }
    ``` 
  - Reducer merupakan fungsi untuk mengolah data.
    ```javascript
    function myReducer(previousState, action) => {
    // use the action type and payload to create a new state based on
    // the previous state.
    return newState;
    }
    ```
      
### Async Actions with Middleware and Thunk
- Redux Thunk adalah middleware yang memungkinkan memanggil pembuat aksi yang mengembalikan fungsi sebagai ganti objek aksi. Fungsi itu menerima metode pengiriman penyimpanan, yang kemudian digunakan untuk mengirim aksi sinkron di dalam isi fungsi setelah operasi asinkron selesai.
- Intalasi Thunk<br>
Untuk menambahkan redux thunk hal yang harus dilakukan adalah:
  - menginstall dependensinnya: `npm install redux-thunk` 
  - Update Redux store agar dapat menggunakan middleware (import thunk from 'redux-thunk')
  - import applyMiddleware (import { createStore, applyMiddleware } from 'redux';)
- Contoh:
    ```javascript
    import React from 'react';
    import ReactDOM from 'react-dom';
    import { Provider } from 'react-redux';
    import { createStore, applyMiddleware } from 'redux';
    import thunk from 'redux-thunk';
    import './index.css';
    import rootReducer from './reducers';
    import App from './App';
    import * as serviceWorker from './serviceWorker';

    // use applyMiddleware to add the thunk middleware to the store
    const store = createStore(rootReducer, applyMiddleware(thunk));

    ReactDOM.render(
    <Provider store={store}>
        <App />
    </Provider>,
    document.getElementById('root')
    );
    ```
