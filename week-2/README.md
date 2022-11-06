# RANGKUMAN WEEK 2 BACK-END BOOTCAMP

## Basic MySQL

- #### Definisi Database

&nbsp;&nbsp;&nbsp;&nbsp;Database adalah kumpulan table elektronik yang terorganisir yang saling memiliki relasi tiap-tiap tablenya, tiap-tiap table memiliki informasi record (isi table) atau data yang kemudian bisa diolah oleh sebuah sistem. Untuk berkomunikasi dengan database diperlukan sebuah software DBMS (Database Management System).

- #### Relational Database

&nbsp;&nbsp;&nbsp;&nbsp;Database relasional adalah kumpulan table dengan hubungan yang telah ditentukan sebelumnya, ada 4 jenis hubungan dalam relasional database yang umumnya digunakan diantaranya:

1. One to Many
2. Many to Many
3. One to One
4. Self Referencing Relationships

Tabel ini digunakan untuk menyimpan informasi tentang record data object yang akan direpresentasikan dalam database. Tiap kolom pada tabel bisa di set dengan jenis data tertentu dengan [MySql data type.](https://www.w3schools.com/sql/sql_datatypes.asp#:~:text=In%20MySQL%20there%20are%20three,numeric%2C%20and%20date%20and%20time) Setiap table biasanya memiliki satu kunci unik/utama yang disebut dengan kunci primer atau primary key, untuk menghubungkan sebuah table dengan table lainnya harus dengan menambahkan kunci asing/foreign key pada table tujuan.

- #### Tipe Data pada MySQL

&nbsp;&nbsp;&nbsp;&nbsp;Pemberian tipe data untuk field atau attribute pada table di maksudkan agar setiap field bisa merepresetasikan nilai dari sebuah attribute baik itu berupa angka (numerik), teks, ataupun berupa waktu. Berikut beberapa tipe data yang bisa digunakan, untuk lebih lengkapnya silahkan ke => [MySql data type.](https://www.w3schools.com/sql/sql_datatypes.asp#:~:text=In%20MySQL%20there%20are%20three,numeric%2C%20and%20date%20and%20time)

| Tipe Data   |                       Kegunaan                       |
| ----------- | :--------------------------------------------------: |
| VARCHAR     | dapat berisikan (string, number dan karakter khusus) |
| TEXT        |                        `GET`                         |
| INT/INTEGER |                        `GET`                         |
| BOOLEAN     |                        `POST`                        |
| FLOAT       |                        `GET`                         |
| TIMESTAMP   |                        `PUT`                         |
| YEAR        |                       `DELETE`                       |
| TIME        |                        `GET`                         |

# RANGKUMAN WEEK 2 BACK-END BOOTCAMP

## Basic MySQL

- #### Definisi Database

&nbsp;&nbsp;&nbsp;&nbsp;Database adalah kumpulan table elektronik yang terorganisir yang saling memiliki relasi tiap-tiap tablenya, tiap-tiap table memiliki informasi record (isi table) atau data yang kemudian bisa diolah oleh sebuah sistem. Untuk berkomunikasi dengan database diperlukan sebuah software DBMS (Database Management System).

- #### Relational Database

&nbsp;&nbsp;&nbsp;&nbsp;Database relasional adalah kumpulan table dengan hubungan yang telah ditentukan sebelumnya, ada 4 jenis hubungan dalam relasional database yang umumnya digunakan diantaranya:

1. One to Many
2. Many to Many
3. One to One
4. Self Referencing Relationships

Tabel ini digunakan untuk menyimpan informasi tentang record data object yang akan direpresentasikan dalam database. Tiap kolom pada tabel bisa di set dengan jenis data tertentu dengan [MySql data type.](https://www.w3schools.com/sql/sql_datatypes.asp#:~:text=In%20MySQL%20there%20are%20three,numeric%2C%20and%20date%20and%20time) Setiap table biasanya memiliki satu kunci unik/utama yang disebut dengan kunci primer atau primary key, untuk menghubungkan sebuah table dengan table lainnya harus dengan menambahkan kunci asing/foreign key pada table tujuan.

- #### Tipe Data pada MySQL

&nbsp;&nbsp;&nbsp;&nbsp;Pemberian tipe data untuk field atau attribute pada table di maksudkan agar setiap field bisa merepresetasikan nilai dari sebuah attribute baik itu berupa angka (numerik), teks, ataupun berupa waktu. Berikut beberapa tipe data yang bisa digunakan, untuk lebih lengkapnya silahkan ke => [MySql data type.](https://www.w3schools.com/sql/sql_datatypes.asp#:~:text=In%20MySQL%20there%20are%20three,numeric%2C%20and%20date%20and%20time)

| Tipe Data   |             digunakan untuk              |
| ----------- | :--------------------------------------: |
| VARCHAR     | nama, nim, kode dengan pengabungan huruf |
| TEXT        |         deskripsi sebuah barang          |
| INT/INTEGER | jumlah barang, harga dan lain sebagainya |
| BOOLEAN     |          kondisi sebuah barang           |
| FLOAT       |         menghitung angka desimal         |
| TIMESTAMP   |             pemberian waktu              |
| YEAR        |             pemberian tahun              |
| TIME        |             pemberian waktu              |

- #### Query SQL sederhana

  - Membuat database

    ```sql
      create database mahasiswa_db
    ```

  - Untuk menggunakan database

    ```sql
      use mahasiswa_db
    ```

  - Membuat table

    ```sql
    create table mahasiswa(
      id int not null primary key auto_increment,
      nim varchar(100) not null primary key,
      nama varchar(100) not null,
      email varchar(100) not null,
      createdAt timestamp not null default current_timestamp
    )engine = InnoDB;
    ```

  - Melihat cara melihat pembuatan table

    ```sql
      -- cara 1
      desc mahasiswa;

      -- cara 2
      show create table mahasiswa;

    ```

  - Menambahkan data pada table

    ```sql
    insert into mahasiswa (nim, nama, email) values
    ("21916042", "Muhammad Arsil Alhabsy", "muhammadarsilalhabsy@gmail.com"),
    ("21916043", "Fulan", "fulan@gmail.com"),
    ("21916043", "Udin", "udin@gmail.com");
    ```

  - Cara melihat record/data isi table

    ```sql
      -- melihat seluruh kolom
      select * from mahasiswa

      -- melihat dengan colom pilihan (nim dan nama)
      select nim, nama from mahasiswa;
    ```

  - Update data pada table mahasiswa

    ```sql
      update mahasiswa
      set
      nama = "Indong",
      email = "indong@gmail.com"
      where nim = '21916042';
    ```
