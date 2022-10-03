# Modul 2 LBE MCI 2022: Database & SQL

- [Database](#database)
  - [Konsep](#konsep-database)
  - [Istilah](#istilah-database)
  - [Key](#key-database)
  - [Database Management System (DBMS)](#dbms-database)
- [SQL](#sql)
  - [Tentang](#tentang-sql)
  - [Tipe Data pada SQL](#tipe-data-sql)
  - [Data Definition Language (DDL)](#ddl-sql)
    - [DDL Database](#ddl-database)
    - [DDL Tabel](#ddl-tabel)
  - [Data Manipulation Language (DML)](#dml-sql)
  - [Latihan](#latihan-sql)
  - [Platform untuk Latihan](#platform-sql)
- [Referensi](#referensi)

# <a name="database"></a>1. Database

## <a name="konsep-database"></a>Konsep Database

### Apa itu database?

<b>Database</b> atau <b>basis data</b> adalah kumpulan data yang dikelola sedemikian rupa berdasarkan ketentuan tertentu yang saling berhubungan sehingga mudah dalam pengelolaannya. Melalui pengelolaan tersebut pengguna dapat memperoleh kemudahan dalam mencari informasi, menyimpan informasi, dan membuang informasi. Perangkat lunak yang digunakan untuk mengelola dan memanggil kueri (<i>query</i>) basis data tersebut disebut dengan sistem manajemen basis data (<i>Database Management System</i>/<b>DBMS</b>).

### <a name="istilah-database"></a>Istilah pada database

- <b>Entitas</b>

  Entitas adalah objek yang mewakili sesuatu dalam dunia nyata dan dapat dibedakan antara satu dengan lainnya (<i>unique</i>). Objek dapat berupa barang, orang, tempat atau suatu kejadian. Misalnya, dosen, mahasiswa, sepeda motor, rumah, pegawai, dan lain-lain.

- <b>Atribut</b>

  Deskripsi/karakteristik dari suatu entitas, berisi penjelasan detail tentang entitas itu sendiri. Misalnya, entitas mahasiswa mempunyai atribut nama, alamat, NRP, <i>email</i>, dan lain-lain.

- <i><b>Field</b></i>

  Tempat atau kolom yang terdapat pada tabel untuk mengisikan salah satu elemen data.

- <i><b>Record</b></i>

  Kumpulan <i>field</i> yang berhubungan satu sama lain dan biasanya dihitung dalam satu baris.

<b>Gambaran untuk membantu memahami istilah pada database</b>

<img src="https://user-images.githubusercontent.com/37539546/131708987-10383a7c-aa2e-47a1-9685-5b6f90ef8650.jpg" width="598.29" height="208.29">

### <a name="key-database"></a>Key pada database

<i>Key</i> adalah elemen <i>record</i> yang dipakai untuk menemukan <i>record</i> tersebut pada waktu akses. <i>Key</i> di dalam database berfungsi sebagai suatu cara untuk mengidentifikasi dan menghubungkan suatu tabel data dengan tabel yang lain. Terdapat beberapa jenis <i>key</i>, yaitu:

- <i><b>Primary key</b></i>

  <i>Field</i> yang mengidentifikasi sebuah <i>record</i> dan bersifat unik (tidak sama atau ganda). <i>Field</i> di sini juga tidak boleh <b>null</b>.

  <img src="https://user-images.githubusercontent.com/37539546/131865844-a7843364-56f5-4f5c-bb4e-616aa092741b.jpg" width="374" height="151.25">

- <i><b>Secondary key</b></i>

  <i>Field</i> yang mengidentifikasi sebuah <i>record</i> dan tidak bersifat unik. Biasanya digunakan secara kombinasi dan hanya bertujuan untuk mengambil data.

  <img src="https://user-images.githubusercontent.com/37539546/131866668-38b49bbf-ed29-4491-90c5-87b7410352d6.jpg" width="418.5" height="153">

- <i><b>Foreign key</b></i>

  <i>Field</i> yang bukan key, tetapi <i>key</i> pada tabel lain (tabel induk). Digunakan untuk menghubungkan suatu tabel dengan tabel lainnya.

  <img src="https://user-images.githubusercontent.com/37539546/131866956-b53732e4-02c4-4b58-b795-e43670c8d412.jpg" width="402.25" height="245">

### <a name="dbms-database"></a>Database Management System (DBMS)

<b><i>Database Management System</i></b> (DBMS) adalah suatu sistem atau perangkat lunak yang dirancang untuk mengelola suatu basis data dan menjalankan operasi terhadap data yang diminta banyak pengguna.

<b>Contoh DBMS</b>:

- Oracle
- MySQL
- Microsoft Access
- PostgreSQL
- Microsoft SQL Server
- BigQuery

# <a name="sql"></a>2. SQL

## <a name="tentang-sql"></a>Tentang SQL

### Apa itu SQL?

SQL (<i>Structured Query Language</i>) adalah sebuah bahasa yang digunakan untuk mengakses data dalam basis data relasional. SQL dapat digunakan untuk mendefinisikan struktur data, pengubahan data, memanipulasi/memperoleh data, pengaturan sekuritas, dan lain lain. SQL dilafalkan dengan membaca tiap karakternya **S Q L** (Es Qi El) atau **Siquel**.

## <a name="tipe-data-sql"></a>Tipe Data pada SQL (BigQuery)

Pada SQL terdapat banyak sekali tipe data yang digunakan untuk atribut. Berikut ini adalah beberapa tipe data yang populer digunakan.

| Tipe Data                                                       | Deskripsi                                                                                                                                       |
| --------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| ARRAY                                                           | An ARRAY is an ordered list of zero or more elements of non-ARRAY values. Elements in an array must share the same type.                        |
| BOOL                                                            | Boolean values are represented by the keywords TRUE and FALSE.                                                                                  |
| DATE                                                            | The DATE type represents a logical calendar date. 0001-01-01 to 9999-12-31.                                                                     |
| TIME                                                            | A TIME value represents a time of day, as might be displayed on a clock. 00:00:00 to 23:59:59.999999                                            |
| DATETIME                                                        | A DATETIME value represents a date and time. 0001-01-01 00:00:00 to 9999-12-31 23:59:59.999999                                                  |
| <b>INT64</b> (INT, SMALLINT, INTEGER, BIGINT, TINYINT, BYTEINT) | Integers are numeric values that do not have fractional components. INT, SMALLINT, INTEGER, BIGINT, TINYINT, and BYTEINT are aliases for INT64. |
| NUMERIC (DECIMAL)                                               | Decimal type values are numeric values with fixed decimal precision and scale                                                                   |
| FLOAT64                                                         | Double precision (approximate) numeric values.                                                                                                  |
| STRING                                                          | Variable-length character data.                                                                                                                 |
|                                                                 | dan masih banyak lagi.... Selengkapnya bisa klik [di sini](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-types)            |

## <a name="ddl-sql"></a>Data Definition Language (DDL)

DDL digunakan untuk mendefinisikan, mengubah, serta menghapus database dan objek-objek yang diperlukan dalam database atau lebih tepatnya **memanipulasi struktur database**. Dalam implementasinya, DDL digunakan untuk membuat dan memanipulasi tabel maupun <i>view</i>. Terdapat dua macam DDL, yaitu:

### <a name="ddl-database"></a>DDL untuk database

1. <b>CREATE DATASET</b>

   <img src="../modul-sql/img/create_dataset_1.png">
   <img src="../modul-sql/img/create_dataset_2.png" width="400">

2. <b>DELETE DATASET</b>

   <img src="../modul-sql/img/delete_dataset.png">

### <a name="ddl-tabel"></a>DDL untuk tabel

1. <b>CREATE TABLE</b> untuk membuat tabel baru pada database.

   ```SQL
   CREATE TABLE demo_sql.mahasiswa (
      nrp STRING,
      nama STRING,
      usia INT64,
      semester INT64,
      ipk INT64
   )
   /* Membuat tabel dengan dengan nama mahasiswa dengan atribut nrp, nama, usia, semester dan ipk */
   ```

2. <b>ALTER TABLE</b> untuk memodifikasi atribut pada tabel yang sudah ada (menambah, mengubah, menghapus).

   <b>ADD</b>

   ```SQL
   ALTER TABLE demo_sql.mahasiswa
   ADD COLUMN tgl_lahir DATE                                         
   /* Menambah atribut baru 'tgl_lahir' pada tabel Mahasiswa */
   ```

   <b>DROP COLUMN</b>

   ```SQL
   ALTER TABLE demo_sql.mahasiswa
   DROP COLUMN tgl_lahir                                                  
   /* Menghapus atribut 'tgl_lahir' pada tabel Mahasiswa */
   ```

   <b>MODIFY COLUMN</b>

   ```SQL
   ALTER TABLE demo_sql.mahasiswa
   ALTER COLUMN ipk SET DATA TYPE FLOAT64
   /* Mengubah tipe data atribut IPK menjadi FLOAT64 */
   ```

3. <b>RENAME TABLE</b> untuk mengganti nama tabel pada database.

   ```SQL
   ALTER TABLE demo_sql.mahasiswa
   RENAME TO mahasiswa_its
   /* Mengganti nama tabel 'mahasiswa' menjadi 'mahasiswa_its' */
   ```

4. <b>DROP TABLE</b> untuk menghapus tabel pada database.
   ```SQL
   DROP TABLE demo_sql.mahasiswa_its                                                     
   /* Menghapus tabel 'mahasiswa' */
   ```

## <a name="dml-sql"></a>Data Manipulation Language (DML)

DML digunakan untuk memanipulasi data yang ada dalam suatu tabel. Berisi berbagai perintah yang dapat digunakan untuk menyisipkan data (INSERT), mengambil data atau query (SELECT), mengubah data (UPDATE) dan menghapus data (DELETE). Beberapa kuerinya antara lain:

1. <b>INSERT</b> untuk memasukkan <i>record</i> baru pada tabel.

   ```SQL
   INSERT demo_sql.mahasiswa (nrp, nama, usia, semester, ipk)
   VALUES('5025201094', 'Reyner', 20, 5, 3.99),
         ('5025201095', 'Kurnia', 21, 6, 3.80)
    /* Menambahkan record yang atributnya
    NRP : 5025201094
    Nama : Reyner
    Usia : 20
    Semester : 5
    IPK : 3.99
    ... */

   ```

2. <b>DELETE</b> untuk menghapus <i>record</i> pada tabel.

   ```SQL
   DELETE demo_sql.mahasiswa
   WHERE nama = 'Reyner'
   /* Menghapus record yang atribut Nama-nya 'Reyner' */
   ```

3. <b>UPDATE</b> untuk memperbarui/mengubah <i>record</i> yang sudah ada pada tabel.

   ```SQL
   UPDATE demo_sql.mahasiswa
   SET Semester = 4
   WHERE Semester = 3
   /* Mengubah record yang atribut Semester-nya '3' menjadi '4' */
   ```

4. <b>SELECT</b> untuk menampilkan/mengambil data dari database. Dapat menggunakan `DISTINCT` jika ingin menampilkan data tunggal (tidak dobel/kembar) ataupun `*` jika ingin menampilkan semua atribut dari suatu tabel.

   ```SQL
   SELECT
      nama, nrp
   FROM
      `encouraging-key-363809.demo_sql.mahasiswa`
   /* Menampilkan data NRP dan Nama dari tabel 'Mahasiswa' */
   ```

   <img src="../modul-sql/img/tanpa_distinct.png" width="150">

   ```SQL
   SELECT DISTINCT
      nama, nrp
   FROM
      `encouraging-key-363809.demo_sql.mahasiswa`
   /* Menampilkan data Usia dari tabel 'Mahasiswa' secara tunggal */
   ```

   <img src="../modul-sql/img/dengan_distinct.png" width="150">

   ```SQL
   SELECT *
   FROM `encouraging-key-363809.demo_sql.mahasiswa`
   /* Menampilkan semua kolom dari tabel 'Mahasiswa' */
   ```

5. <b>WHERE</b> untuk filter suatu <i>record</i>.

   ```SQL
   SELECT 
      nama, usia
   FROM
      `encouraging-key-363809.demo_sql.mahasiswa`
   WHERE
      usia = 20
   /* Menampilkan data Nama dengan Usia '20' */
   ```

6. <b>BETWEEN</b> untuk operator rentang nilai.

   ```SQL
   SELECT
      nama, usia
   FROM
      `encouraging-key-363809.demo_sql.mahasiswa`
   WHERE
      usia BETWEEN 18 AND 20
   /* Menampilkan data nama dengan Usia '18-20' */
   ```

7. <b>ORDER BY</b> untuk menampilkan <i>record</i> secara <i>ascending</i> (naik) maupun <i>descending</i> (turun).

   ```SQL
   SELECT
      nama
   FROM
      `encouraging-key-363809.demo_sql.mahasiswa`
   ORDER BY
      nama ASC
   /* Menampilkan data Nama dengan urutan ascending */
   ```

   ```SQL
   SELECT
      nama
   FROM
      `encouraging-key-363809.demo_sql.mahasiswa`
   ORDER BY
      nama DESC;
   /* Menampilkan data Nama dengan urutan descending */
   ```

8. <b>MIN</b> dan <b>MAX</b> untuk menampilkan nilai terkecil (minimum) dan nilai terbesar (maksimum).

   ```SQL
   SELECT
      MIN(usia)
   FROM
      `encouraging-key-363809.demo_sql.mahasiswa`
   /* Menampilkan Usia termuda */
   ```

   ```SQL
   SELECT
      MAX(semester)
   FROM
      `encouraging-key-363809.demo_sql.mahasiswa`
   /* Menampilkan Semester paling akhir */
   ```

9. <b>COUNT</b>, <b>AVG</b>, dan <b>SUM</b> sebagai fungsi agregasi. <br>- `COUNT()` untuk menghitung jumlah baris yang sesuai dengan kriteria. <br>- `AVG()` untuk menghitung rata-rata data kolom yang bertipe data numerik. <br>- `SUM()` untuk menghitung total data dalam kolom yang bertipe data numerik.

   ```SQL
   SELECT
      AVG(usia)
   FROM
      `encouraging-key-363809.demo_sql.mahasiswa`
   /* Menampilkan rata-rata Usia */
   ```

   ```SQL
   SELECT
      COUNT(nama)
   FROM
      `encouraging-key-363809.demo_sql.mahasiswa`
   /* Menampilkan jumlah baris atribut Nama */
   ```

   ```SQL
   SELECT
      SUM(ukt)
   FROM
      `encouraging-key-363809.demo_sql.mahasiswa`
   /* Menampilkan jumlah total data dari atribut UKT */
   ```

10. <b>GROUP BY</b> untuk mengelompokkan baris yang memiliki nilai yang sama. Biasanya digunakan bersamaan dengan fungsi agregasi.

    ```SQL
    SELECT
      usia, COUNT(nama) AS jumlah
    FROM
      `encouraging-key-363809.demo_sql.mahasiswa`
    GROUP BY usia
    /* Menampilkan jumlah Nama berdasarkan Usia */
    ```

## <a name="latihan-sql"></a>Latihan

Sebelum mengerjakan, kalian dapat mengunduh dataset <b>Mahasiswa</b> [di sini](https://drive.google.com/file/d/1Kr6bl-of_BD8uKSojAcZSG1JJkCzDihj/view?usp=sharing "di sini"). Setelah itu di-<i>import</i> ke BigQuery.

1. Tampilkan daftar nama dan ukt berdasarkan nominal ukt yang paling mahal!

   <img src="../modul-sql/img/no_1.png" width=300px>

2. Tampilkan daftar nama dan ukt berdasarkan nominal ukt yang paling mahal, jika ada ukt yang sama, urutkan berdasarkan nama mahasiswa secara alfabetikal.

   <img src="../modul-sql/img/no_2.png" width=300px>

3. Hitunglah jumlah mahasiswa yang memiliki ipk >= 3.5 dan berada di semester 8

   <img src="../modul-sql/img/no_3.png" width=200px>

SOAL TANTANGAN!

4. Tampilkan daftar nama, semester dan ipk berdasarkan ipk tertinggi tiap semester. Diurutkan berdasarkan semesternya. Jika ada yang nilainya sama, maka diurutkan berdasarkan alfabet.

   <img src="../modul-sql/img/no_4.png" width=300px>

## <a name="platform-sql"></a>Platform untuk Latihan

1. https://console.cloud.google.com/bigquery

## <a name="referensi"></a>Referensi

- https://www.dicoding.com/blog/apa-itu-database/
- https://informatika.poltektegal.ac.id/?p=bidang-keilmuan&s=database
- http://www.pengertianku.net/2014/12/pengertian-field-record-table-file-data-dan-basis-data-lengkap.html
- https://www.dumetschool.com/blog/perbedaan-primary-key-foreign-key-dan-candidate-key
- https://www.w3schools.com/sql
- https://www.dewaweb.com/blog/sql-pengertian-fungsi-beserta-perintah-dasarnya/
- https://id.wikipedia.org/wiki/SQL
- https://teachcomputerscience.com/database-data-types/
- https://github.com/minons1/PelatihanSoftwareHouseHMTCITS/wiki
- https://github.com/irsyadhani/LBE_MCI-Modul_SQL
- https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language
- https://cloud.google.com/bigquery/docs/reference/standard-sql/dml-syntax
