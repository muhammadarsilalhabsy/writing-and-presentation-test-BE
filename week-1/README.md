# RANGKUMAN WEEK 1 BACK-END BOOTCAMP

## Web Server

- #### Definisi

&nbsp;&nbsp;&nbsp;&nbsp;Web server memiliki dua buah komponen yang penting yaitu hardware dan software. Web server ini memungkinkan developer Front-end ataupun Back-end untuk menjalankan hasil codingan mereka, salah satu contoh web server adalah Apache. Untuk melakukan interaksi dengan web server bisa menggunakan protocol HTTP (Hypertext Transfer Protocol).

- #### Metode request yang digunakan pada project ini

  ##### Single page application & CSR (Client Side Rendering)

&nbsp;&nbsp;&nbsp;&nbsp;Single page application adalah sebuah konsep web yang memiliki satu halaman saja. CSR adalah sebuah method dalam membuat suatu website dimana website akan dirender di dalam browser cliet/user bukan pada server. Data yang direquest oleh user berupa JSON, JSON yang dikirim oleh server akan diterima dan ditampilkan pada halaman yang sudah disediakan oleh Front-end dan tidak akan mengubah atau menimpah halaman sebelumnya.

- #### API Architecture Style

1. [REST](https://restfulapi.net/) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;:heavy_check_mark:
2. [GraphQL](https://graphql.org/learn/) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; :x:
3. SOAP &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;:x:
4. RPC &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;:x:

- #### REST API

&nbsp;&nbsp;&nbsp;&nbsp;REST atau **REpresentational State Transfer** merupakan salah satu architecture design untuk membuat web services. REST adalah architecture style sedangkan RESTful API adalah API yang menerapkan ke 6 rules/principal dari REST architecture seperti yang dibawah ini.

1.  uniform interface
2.  client-server
3.  stateless
4.  cacheable
5.  layered system
6.  code on demand (optional)

- #### HTTP Method

&nbsp;&nbsp;&nbsp;&nbsp;[HTTP Method](https://restfulapi.net/http-methods/) bertujuan sebagai penanda untuk melakukan request pada server, baik itu mengambil data, mengirim data, menghapus data, merubah data dan lain sebagainya. berikut beberapa HTTP Method yang akan dipelajari:

1. get (mengambil data)
2. post (menambah data)
3. put (mengupdate data)
4. patch (mengupdate data secara partial/sebahagian juga bisa mereplace data)
5. delete (menghapus data)

- #### HTTP Status Code

&nbsp;&nbsp;&nbsp;&nbsp;[Status code](https://restfulapi.net/http-status-codes/) merupakan kode kode response standard yang diberikan oleh server, yang bertujuan untuk mengetahui apakah perintah yang dikirimkan oleh client berhasil atau tidak. Berikut adalah code response standar (100-599):

- 1xx (informational)
- 2xx (success)
- 3xx (rejected)
- 4xx (client error)
- 5xx (server error)

- #### Resouce Naming

&nbsp;&nbsp;&nbsp;&nbsp;Strategy penamaan resouce yang baik dan konsisten akan membuat REST resouce kita akan kokoh dan juga support penggunaan jangka panjang. berikut detail tentang [Resource naming](https://restfulapi.net/resource-naming/)

| Secenario                        | HTTP Method |   URI Format    |
| -------------------------------- | :---------: | :-------------: |
| Mengambil seluruh data customers |    `GET`    |   /customers    |
| Mengambil data customers by id   |    `GET`    | /customers/{id} |
| Menambah customers               |   `POST`    |   /customers    |
| Mengupdate data customers by id  |    `PUT`    | /customers/{id} |
| Menghapus data customers by id   |  `DELETE`   | /customers/{id} |

&nbsp;

## Intro Node JS

- #### Definisi

&nbsp;&nbsp;&nbsp;&nbsp;Node Js adalah JavaScript runtime yang dibanggun diatas JavaScript engine V8 punya Chrome. Node js juga open source dan cross platform yang bisa di run/jalankan di luar web browser artinya bisa dijalankan tanpa menggunakan web browser seperti operation system. Selain itu Node JS bisa digunakan sebagai server-side-scripting untuk menjalankan dinamic web content. Teknologi ini diciptakan oleh [Rayan Dhal](https://en.wikipedia.org/wiki/Ryan_Dahl) pada tahun 2009.

- #### Main Feature

1. File System
2. HTTP & HTTPs
3. REPL (Read, Eval, Print, Loop)
4. Console

- #### Module NodeJS

1. os module

&nbsp;&nbsp;&nbsp;&nbsp;Melihat mesin dan home directory pada sistem operasi saya.

![os module](../assets/os.png 'os module result')

2. events module

&nbsp;&nbsp;&nbsp;&nbsp;Mirip seperti DOM pada JavaScript, events module memugkinkan kita untuk menambahakn listener, dengan menggunakan method `emmiter.on('nama_event, callback)` dan di trigger dengan menggunakan `emitter.emit('nama_event', value_callback)`

![events module](../assets/events.png 'events module result')

3. http module

&nbsp;&nbsp;&nbsp;&nbsp;Membuat server dengan memberikan response `Hallo guys!` pada browser dengan alamat http://localhost:8070

![http module](../assets/http%20module.png 'http module result')

- #### npm run

&nbsp;&nbsp;&nbsp;&nbsp;Teknik ini digunakan untuk mempermudah saat mengeksekusi kodingan

![os module](../assets/menggunakan%20npm%20run.png 'events module result')

## ExpressJS

- #### Definisi

&nbsp;&nbsp;&nbsp;&nbsp;ExpressJS merupakan framework open source dan gratis dari NodeJS yang bertugas membantu tahap pengembangan aplikasi dari sisi back-end baik itu web maupun mobile application

> Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.

- #### Instalasi & penggunaan

1. inisialisasi npm : `npm init`
2. instal express : `npm i express`
3. code view:

![express module](../assets/express.png 'keneksi ke port 80000')

4. Menggunakan npm nodemon ke dev : `npm i --save-dev nodemon atau npm i -D nedemon`

![nodemon module](../assets/nodemon.png 'nodemon')

- #### Middleware

&nbsp;&nbsp;&nbsp;&nbsp;Middleware adalah sebuah aturan atau prosedur-prosedur yang harus dilewati. middelware memiliki aksess ke object req, res, dan next.

code view (biasa):

![middleware](../assets/post.png 'menambah data menggunakan post melalui middleware')

code view (modular):

![middleware](../assets/modular%20routes.png 'modular get data')

&nbsp;

## Design Databases

![desing databases](../assets/diagram%20databases.png 'databases diagram')
