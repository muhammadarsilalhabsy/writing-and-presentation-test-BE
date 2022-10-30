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

&nbsp;&nbsp;&nbsp;&nbsp;Strategy penamaan resouce yang baik dan konsisten akan membuat REST resouce kita akan kokoh dan support penggunaan jangka panjang. berikut detail tentang [Resource naming](https://restfulapi.net/resource-naming/)

&nbsp;

| Secenario                        | HTTP Method |   URI Format    |
| -------------------------------- | :---------: | :-------------: |
| Mengambil seluruh data customers |    `GET`    |   /customers    |
| Mengambil data customers by id   |    `GET`    | /customers/{id} |
| Menambah customers               |   `POST`    |   /customers    |
| Mengupdate data customers by id  |    `PUT`    | /customers/{id} |
| Menghapus data customers by id   |  `DELETE`   | /customers/{id} |
