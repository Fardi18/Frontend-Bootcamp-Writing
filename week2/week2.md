# Front-end Bootcamp Week 2

- ## PropTypes

  Proptypes adalah sebuah library yang dapat membantu kita untuk memeriksa tipe data props yang dikirim agar sesuai dengan apa yang kita inginkan, kita dapat mengirim pesan eror jika data yang dikirim tidak sesuai dengan apa yang diharapkan. <br>
  Contohnya saat kita menginginkan data umur maka kita membutuhkan data dengan tipe number, tetapi jika props mengirim data string, kita bisa mengirimkan pesan error. <br>

  - Cara menggunakan PropTypes <br>
    1. Buka terminal dan ketikkan `npm install prop-types` <br>
    2. Import PropTypes tadi ke dalam project kita. `import PropTypes from "prop-types"` <br>
    3. Panggil fungsi yang kita buat dan ketikkan code sebagai berikut : <br>
    ```javascript
    // mengatur props-types
    StudentInfo.propTypes = {
      name: PropsTypes.string,
      age: PropsTypes.number,
    };
    ```
    <br>
  - Beberapa PropTypes yang bisa digunakan <br>

    1. `.string` : untuk menentukan data berupa string <br>
    2. `.number` : untuk mementukan data berupa number <br>
    3. `.any` : untuk mementukan data berupa data type apa saja <br>
    4. `.isRequired` : data harus ada/diisi <br>
    5. `oneOfType` : untuk memberikan beberapa pilihan data type <br>
    6. `array` : untuk menentukan data berupa array <br>
    7. `arrayOf` : untuk mengecek value dari prop <br>
    8. Dan masih banyak lainnya. <br>

<br><br><br>

- ## Router

  React Router adalah sebuah library dari React yang digunakan untuk membantu kita membuat rute pada website yang SPA (Single Page Application) sehingga website yang kita buat menjadi terlihat memiliki beberapa halaman dan user bisa berpindah-pindah halaman. <br>

  - Cara install React-router <br>

    1. Buka terminal dan ketikkan `npm install react-router-dom` <br>
    2. Import librarynya di dalam file `main.js` <br>

    ```javascript
    // main.js
    import { createBrowserRouter RouterProvider, Route, } from "react-router-dom";
    ```

    3. Bungkus `<App />` dengan `BrowserRouter` di dalam file `main.js`

    ```javascript
    // main.js

    <BrowserRouter>
      <App />
    </BrowserRouter>
    ```

    4. Import library di dalam file `App.jsx` <br>

    ```javascript
    // App.jsx

    import { Routes, Route, Link } from "react-router-dom";
    ```

    5. Panggil yang sudah di-import di dalam return file `App.jsx`. Siapkan terlebih dahulu beberapa page dan component yang dibutuhkan
       <br>

    ```javascript
    // App.jsx

    return (
      <>
        <nav>
          <Link to={"/"}>Home |</Link>
          <Link to={"/about"}>About</Link>
        </nav>
        <Routes>
          <Route path="/" element={<HomePage />} />
          <Route path="/" element={<AboutPage />} />
        </Routes>
      </>
    );
    ```

    <br>

  - Params <br>
    Params digunakan untuk mengirim parameter/data lewat router. <br>

    ```javascript
    // App.jsx

    return (
      <>
        <nav>
          <Link to={"/"}>Home |</Link>
          <Link to={"/about"}>About</Link>
        </nav>
        <Routes>
          <Route path="/" element={<HomePage />} />
          <Route path="/" element={<AboutPage />} />
          // params dengan ciri-ciri (:id) yang bisa mengakses/mengirim data sesuai dengan id-nya
          <Route path="/detail/:id" element={<DetailPage />} />;
        </Routes>
      </>
    );
    ```

    <br>

  - Nested Router <br>
    Nested Router berarti terdapat route di dalam route. <br>
    Langkah-langkah membuat Nested Route <br>

    1. Buka file `App.jsx` dan masukkan code berikut : <br>

    ```javascript
    // App.jsx

    return (
      <>
        <nav>
          <Link to={"/"}>Home |</Link>
          <Link to={"/about"}>| About</Link>
        </nav>

        <Routes>
          <Route path="/" element={<Home />} />

          {/* Params */}
          <Route path="/detail/:id" element={<Detail />} />

          {/* Nesterd Route */}
          <Route path="/about" element={<About />}>
            <Route path="student" element={<AboutStudent />} />
            <Route path="teacher" element={<AboutTeacher />} />
          </Route>
        </Routes>
      </>
    );
    ```

    2. Buka file `About.jsx` lalu masukkan code berikut : <br>

    ```javascript
    // About.jsx

    import { Outlet, Link } from "react-router-dom";

    const AboutPage = () => {
      return (
        <>
          // Outlet berfungsi untuk menampilkan child (student dan teacher) yang dimiliki parentnya (About.jsx)
          <Outlet />
          <Link to={"student"}>About Student |</Link>
          <Link to={"teacher"}> About Teacher</Link>
        </>
      );
    };

    export default About;
    ```

<br><br><br>

- ## Redux
  ![ilustrasi](https://www.rlogical.com/wp-content/uploads/2021/07/Bildschirmfoto-2017-12-01-um-08.53.32.png)
  Redux adalah sebuah state management yang dapat membantu kita dalam mengatur data/state yang kita miliki. Ide dari redux adalah menyimpan state di suatu tempat sehingga lebih mudah di atur dan memudahkan dalam komunikasi data antar komponen. <br>
  Redux biasanya dipakai jika aplikasi atau website yang kita buat sudah berskala besar dan kompleks. <br>
  Terdapat beberapa istilah dalam Redux : Store, Reducer, Action, dll. <br>
  - Store <br>
    Store adalah tempat dimana kita menyimpan semua state yang kita miliki. Jadi store ibarat database untuk frontend. <br>
  - Reducer <br>
    Reducer adalah sebuah fungsi yang tugasnya untuk mengolah state yang ada di store. Reducer diibaratkan sebagai rak yang ada di dalam sebuah Store. Misal menambah data, menghapus data, mengambil data, dsb. Ada 2 parameter wajib dari reducer, yaitu state dan action. <br>
  - Action <br>
    Action adalah sebuah function yang mereturn sebuah objek. Objek tersebut memiliki sebuah property wajib yaitu type. Type inilah yang menentukan bagaimana statenya akan diubah. <br>
  - Cara menggunakan Redux <br>
    1. Buka terminal dan install redux dan react-redux : `npm nstall redux react-redux` <br>
    2. Import redux dan react-reduxnya <br>
    3. Buat folder `redux` di dalam folder `src` <nr>
    4. Buat folder `store` di dalam folder `redux`, dan file .js-nya dengan `createStore` dengan parameter `reducer` <br>
    5. Buat folder `reducer` di dalam folder `reducer`dan file .js-nya <br>
    6. Buat `initialState` di dalam `reducer`, jangan lupa tentukan default valuenya <br>
    7. Buat `function switch`di dalam `reducer` dengan defaultnya `return state` <br>
    8. Bungkus `App.jsx` dengan `Provider` di dalam file `main.jsx` <br>
    9. Buat Component yang dibutuhkan <br>
    10. Buat `actions` di dalam folder `action` dimana folder action ini ada di dalam folder `redux` <br>

<br><br><br>

- ## Redux-Thunk
  Redux Thunk adalah sebuah middleware yang memungkinkan kita untuk menulis action yang mengembalikan function. <br>
  Dengan thunk kita bisa menjalankan fungsi async seperti memanggil API. <br>
  Thunk untuk membantu proses yg delay (asynchronus) pada dispatch <br>
  - Cara install Thunk <br>
    1. Buka terminal dan ketikkan : <code>npm install redux react-redux redux-thunk</code> <br>
    2. Jangan lupa import di file yang kita miliki
