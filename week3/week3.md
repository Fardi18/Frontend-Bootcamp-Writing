# React Lanjutan

- ## React Context

  ### Pengertian React Context

  React Context merupakan bawaan dari React JS (tidak perlu diinstall pada terminal) yang mirip dengan Redux yaitu untuk mengatasi props drilling dan juga state management. <br>
  Context akan membuat suatu variable menjadi bersifat global <br>
  Untuk menggunakannya kita cukup memanggilnya dengan import dan membuat sebuah component context-nya. <br>
  Component context ini yang akan menyediakan data (provide) untuk semua component yang ada. <br>

  ### Kapan React Context digunakan?

  Penggunaan React Context sebenarnya tidak wajib, tetapi kita bisa menggunakan React Context jika aplikasi website yang kita bangun ini masih berskala kecil sampai menengah. <br>

  ### Hal yang perlu di-import untuk menggunakan React Context

  - createContext : untuk membuat context <br>
  - useContext : untuk memanggil data oada component lain <br>
  - useReducer : membuat variable/data menjadi global

- ## React Testing

  Terdapat dua tipe testing :

  1. Manual : melakukan check kepada code-code kita secara manual, dan <br>
  2. Automation : yaitu testing yang dilakukan dengan code yang kita buat khusus untuk testing <br>

  ### Testing Automation

  Dibagi menjadi 3 bagian :

  1. End to End, testing yang melibatkan user.
  2. Integration, melakukan pengujian jika kita memiliki third party, dll.
  3. Unit, menguji bagian-bagian kecil di dalam source code kita. <br>
     > End to End memiliki harga yang paling mahal dengan kecepatan testing paling lama, dan Unit Testing adalah sebaliknya.
     > <br>

  ### Jest

  Jest adalah testing framework dengan jargon “Painless Javascript Testing”. testing framework besutan Facebook ini mempunyai kelebihan tersendiri pada running test suits-nya yang cepat. Jest adalah library JS yang digunankan untuk proses testing. <br>
  Untuk menggunakannya install terlebih dahulu dengan cara `npm i --save-dev jest` pada terminal <br>

  ### RTL (React Testing Library)

  RTL merupakan testing bawaan dari React JS.
