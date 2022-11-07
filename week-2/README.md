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

&nbsp;&nbsp;&nbsp;&nbsp;Perintah SQL dibagi menjadi 3 sub yaitu:

1. **DDL** (Data Definition Language)
   - create
   - rename
   - alter
   - drop
2. **DML** (Data Manipulation Language)
   - select
   - insert
   - update
   - delete
3. **DCL** (Data Control Language)
   - grant
   - revoke

&nbsp;&nbsp;&nbsp;&nbsp;Query database sederhana yang akan tampilkan berikut merupakan kombinasi DDL dan DML, mulai dari membuat database, table, insert data sampai dengan delete data pada table.

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

- Delete data pada table mahasiswa

  ```sql
  delete from mahasiswa
  where nim = '21916043';
  ```

## MySQL Lanjut

- #### Membuat database yang berrelasi

  **Desain table:**

  ![desain diagram](../assets/table-berrelasi.png 'deasain diagram')

  **Implementasi query:**

  ```sql
  -- membuat database
  create database store;

  -- menggunakan database
  use store;

  -- create table category
  create table category (
    id varchar(10) not null primary key,
    name varchar(50) not null
  )engine = innodb; -- optional untuk menambahkan engine

  -- create table products
  -- table products memiliki relasi one to many dari (category)
  create table products(
    id int not null primary key auto_increment,
    name varchar(100),
    price int unsigned not null default 0,
    category_id varchar(10),
    foreign key (category_id) references category(id)
  );

  -- create table customers
  create table customers(
    id int not null auto_increment,
    name varchar(100) not null,
    email varchar(100) not null,
    primary key(id)
  );

  -- alter table add constraint
  alter table customers
  add constraint email_unique unique (email);

  -- create table wishlist
  -- table wishlist ini memiliki relasi many to many dari (customers dan products)
  create table wishlist (
    id int not null auto_increment primary key,
    customers_id int not null,
    products_id int not null,
    foreign key (customers_id) references customers(id);
  );

  -- menambahkan foreign key melalui alter table
  alter table wishlist
  add foreign key (products_id) references products(id);

  ```

- Menambahkan data pada tiap-tiap table

  ```sql
  insert into customers (name, email) values
  ("arsil","arsil@gmail.com"),
  ("ucup","ucup@gmail.com"),
  ("jamal","jamal@gmail.com"),
  ("nova","nova@gmail.com");

  insert into category(id, name) values
  ('c0001',"makanan"),
  ('c0002',"minuman"),
  ('c0003',"bahan dapur"),
  ('c0004',"alat mandi"),
  ('c0005',"bahan cuci"),
  ('c0006',"permen"),
  ('c0007','lain-lain');

  insert into products (name, price, category_id) values
  ('Mie Kaldu',2500,"c0001"),
  ('Ayam goreng',2000,"c0001"),
  ('Mie Goreng',3000,"c0001"),
  ('Daia',6000,"c0005"),
  ('Pepsodent',12000,"c0004");

  insert into wishlist (customers_id, products_id) values
  (1,5),
  (1,4),
  (1,6),
  (3,4),
  (3,3),
  (2,5),
  (4,5),
  (4,3);
  ```

- Melakukan operasi pada table yang memiliki relasi

  ```sql

  -- tambilkan id, nama, price dari table products dan juga tampilkan category name dari table category yang saling memiliki hubungan.
  select p.id, p.name, p.price, c.name as 'category name'
  from products as p inner join category as c
  on p.category_id = c.id;

  -- tampilkan nama customer & nama products pada table wishlist
  -- lalkukan inner join pada table customers dan products
  select c.name as "pemilik", p.name as "products" from wishlist
  inner join customers as c
  on wishlist.customers_id = c.id
  inner join products as p
  on wishlist.products_id = p.id;

    -- menghitung average price
  select avg(price) from products;

    -- menghitung total price
  select sum(price) from products p ;

    -- meghitung harga yang paling tertinggi
  select max(price) from products

    -- meghitung banyak tiap-tiap category pada table products menggunakan group by
  select count(category_id) from products group by category_id  ;

  select c.name as 'category name', count(category_id) as 'total use'
  from products as p
  inner join category as c
  on p.category_id = c.id
  group by p.category_id;

  ```

- Wildcard & Like

  ```sql
  -- mencari data dengan awalan kata sampo
  select id, name, price from products where name like 'sampo%';

  -- mencari data yang menggandung kata 'gor'
  select id, name, price from products where name like '%gor%';

  -- mencari data dengan akhiran kata 'ng'
  select id, name, price from products where name like '%ng';

  ```

## Authentication and Authorization

- #### Perbedaan Authentication, Authorization dan Encryption

&nbsp;&nbsp;&nbsp;&nbsp;**Authentication**/Otentikasi adalah sebuah proses pengkonfirmasian atau proses validasi data diri atas identitas yang sudah dimiliki oleh pengguna sebelumnya, Authentication biasanya dilakukan pada saat ingin melakukan login, sedangkan **Authorization**/Otorisasi merupakan sebuah proses untuk menentukan apakah pengguna yang meminta izin masuk telah diberikan hak akses dari sumber daya yang memiliki wewenang tertinggi (admin). Berdedan dengan Authentication dan Authorization, **Encryption** adalah satu teknik yang digunakan untuk mengubah kalimat yang bisa dibaca oleh manusia menjadi kode kode rahasia yang dilakukan pada proses `encode`, kode rahasia ini bisa dikembalikan lagi ke satu kalimat yang bisa dibaca dengan melakukan proses `decode`.

- #### Membuat Authentication menggunakan JWT (Json Web Token)

  - Install: `npm install jsonwebtoken`
  - Add: `require('jsonwebtoken')`
  - Craete screate key: `const SCREATE_KEY = 'rahasia';`
  - add: `const token = jwt.sign(data.username, SECREATE_KEY);`

code example:

![auth](../assets/jwt.png 'auth using jwt')

## Sequalize

- #### Definisi dan fungsi Sequalize

&nbsp;&nbsp;&nbsp;&nbsp;**Sequelize** adalah Node.js promise-based ORM untuk beberapa DBMS. Lalu apa itu ORM?. ORM (Object Relation Mapping) merupakan satu teknik merubah table menjadi sebuah object yang nantinya mudah untuk digunakan untuk dimodifikasi. Manfaat menggunakan Sequelize yaitu kita bisa mengelola sumber daya pada table, baik itu relasi-relasi pada table maupun data di database kita dengan cepat, dan efisien. berikut adalah DBMS yang bisa menggunakan Sequelize diantaranya:

1. MySQL,
2. PostgreSQL,
3. SQLite,
4. MSSQL
5. dan database SQL lainnya.

- #### Membuat sequelize-cli

1. `npm install --save-dev sequelize-cli`
2. `npx sequelize-cli init`
3. `npm install --save mysql2` (jika menggunakan pake mysql)
4. setting configuration:

![config-json-sequelize](../assets/config-json.png 'config-json-sequelize')

5. membuat model: `npx sequelize-cli model:generate --name User --attributes id:integer,email:string,firstName:string,lastName:string,email:string`
6. `npx sequelize-cli db:migrate`

code result (hasil migrasi):

![generate table users](../assets/generate-table-users.png 'generate table users')
