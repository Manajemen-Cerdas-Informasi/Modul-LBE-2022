# Modul 2 LBE MCI 2022: Data Preprocessing

- [Data Preprocessing](#data-preprocessing)
  - [Definisi](#definisi)
  - [Keuntungan](#keuntungan)
- [Data Preprocessing dengan SQL](#dp-with-SQL)
  - [Mencari Record dengan Values yang Hilang](#2-1)
  - [Melakukan Flag pada Record](#2-2)
  - [Membersihkan Kumpulan Value yang Terlalu Beragam](#2-3)
  - [Mengategorikan Value Sesuai dengan Interval](#2-4)
  - [Membenarkan Data Type](#2-5)
- [Data Preprocessing dengan Python](#dp-with-python)
  - [Import Dataset](#3-1)
  - [Mencari dan Mengisi Data Hilang](#3-2)
  - [Menghapus data duplikat](#3-3)
  - [Membersihkan format data](#3-4)
- [Latihan](#latihan)
- [Referensi](#referensi)

## <a name="data-preprocessing"></a>1. Data Preprocessing

### <a name="definisi">Apa itu data preprocessing?

Dalam dunia nyata, programmer akan banyak menemukan set data yang bersifat kotor. Set data yang bersifat kotor adalah set data yang ditulis dengan format yang tidak seragam, tidak memiliki tipe data yang sesuai, memiliki banyak field yang kosong ataupun terkorupsi. Hal ini akan menjadikan set-set data tersebut sulit untuk diinterpretasikan, divisualisasikan ataupun diproses dengan business intelligence untuk keperluan-keperluan tertentu.

<b>Data preprocessing</b> atau data cleaning adalah proses manipulasi, penghapusan, penggantian atau penambalan data kepada set data sehingga set data dapat mengakomodasi pemrosesan data lebiih lanjut. Selain itu, data preprocessing juga memiliki peran penting dalam menyiapkan data-data yang dapat diandalkan dengan menerapkan proses analitik yang sesuai dengan ilmu atau teori yang ada kepada set data yang bersifat kotor.

![image](https://user-images.githubusercontent.com/34309557/194705405-98b45cdc-e505-4d72-b0d2-fe80b3129800.png)

### <a name="keuntungan">Keuntungan dari data preprocessing

Data preprocessing memiliki banyak keuntungan. Beberapa poin penting dalam kelebihan data preprocessing adalah sebagai berikut

<b>1. Error-Free Data</b>

Ketika set data terdiri dari kumpulan data yang berasal dari sumber yang berbeda, akan terdapat kemungkinan format data pada kolom yang sama berbeda dengan satu sama lainnya. Hal ini akan mengakibatkan eror apabila data set tersebut ingin diproses atau divisualisasikan karena komputer hanya dapat menerima kumpulan data dalam satu kolom dengan pemformatan yang seragam.

![image](https://user-images.githubusercontent.com/34309557/194706309-96ed1996-0ee8-4060-90c7-f912f0dab835.png)

<b>2. Data Quality</b>

Terkadang, suatu kolom pada set data harus mengikuti aturan yang sesuai dengan keperluan. Seperti data dengan tipe data boolean yang hanya boleh memiliki nilai 0 dan 1 ataupun alamat email yang harus memiliki simbol @ atau . diantara beberapa kata kunci. Ada beberapa kasus yang mana pengguna dapat memasukkan data yang tidak sesuai dengan constraints atau aturan-aturan yang berlaku.

<b>3. Accurate and Efficient</b>

Permasalahan ril membutuhkan back-up data yang juga bersifat ril. Maka dari itu, suatu set data juga harus memiliki nilai-nilai yang benar. Hal ini dapat dilakukan dengan menghapus record data yang memiliki field-field kosong atau memiliki field data yang tidak berkualitas sehingga data dari record tersebut tidak mempengaruhi hasil interpretasi atau visualisasi data.

<b>4. Complete Data</b>

Pada keadaan tertentu, untuk dapat memroses suatu set data, set data tersebut harus bersifat komplit. Seperti pada set data yang memiliki keperluan untuk mengontak orang yang terdaftar, maka field untuk nomor telepon tidak boleh kosong. Maka dari itu, data preprocessing juga mengandung proses untuk melengkapi data, baik dilakukan secara manual (mengontak orang yang bersangkutan/mengadakan pengisian form kembali) ataupun dilakukan secara otomatis oleh suatu intelligent system.

<b>5. Maintains Data Consistency</b>

Untuk memastikan bahwa suatu record bersifat konsisten, kita dapat melakukan komparasi suatu record dengan premis yang berlaku atau dengan record lainnya. Seperti contoh, apabila kita memiliki suatu record yang menyatakan bahwa baju dengan harga `Rp10.000` berada di kategori `Mahal`, kita perlu melakukan cross-check kepada record lain dan melihat apakah memang baju berharga `Rp10.000` dikategorikan sebagai `Mahal` dalam set data tersebut. Apabila tidak, kita harus melakukan preprocessing dan memanipulasi data tersebut supaya menjadi benar dan konsisten.

<img src="https://user-images.githubusercontent.com/34309557/194706298-59152a93-1d79-4637-be9c-7def3401696b.png" width="600">


## <a name="dp-with-SQL"></a>2. Data Preprocessing dengan SQL

Data preprocessing dapat dilakukan dengan banyak cara, baik menggunakan python, SQL, pendekatan manual (mengadakan kuesioner kembali) ataupun dengan tools lainnya yang dapat membersihkan set data. Pada section ini, kita akan belajar data preprocessing dengan SQL.

### <a name="2-1">2.1. Mencari Record dengan Values yang Hilang

Cara mencari record yang memiliki nilai null pada suatu field adalah dengan menggunakan sintaks `WHERE <column> IS NULL`. Berikut ini adalah contoh penggunaannya.

```
SELECT OrderID,
       Sales_Manager,
       Product_Category,
       Shipping_Address
FROM Sales_Data
WHERE Product_Category IS NULL
```

![image](https://user-images.githubusercontent.com/34309557/194705315-a3915fa7-d2c3-4116-a2a2-29901f2d95f1.png)

### <a name="2-2">2.2. Melakukan Flag pada Record

Selain dengan kueri di atas, kita juga bisa memberi tanda/flag kepada record-record yang bermasalah. Berikut ini adalah contoh kueri yang akan memberikan flag kepada record yang field `Delivery_Time` sama dengan `NULL`

```
SELECT OrderID,
       Sales_Manager,
       Shipping_Address,
       Delivery_Time,
       CASE WHEN Delivery_Time IS NULL THEN 1
            ELSE 0
       END AS Dirty_data
FROM Sales_Data
```

![image](https://user-images.githubusercontent.com/34309557/194705602-ba9611d1-8d94-4c03-8e5d-522192771c7b.png)

Kueri tersebut akan menghasilkan tabel baru dalam view yang memiliki kolom `Dirty_data`. Hal ini dapat memudahkan pencarian record yang memiliki nilai `NULL` dengan kueri sebagai berikut.

```
SELECT OrderID,
       Sales_Manager,
       Shipping_Address,
       Delivery_Time,
       CASE WHEN Delivery_Time IS NULL THEN 1
            ELSE 0
       END AS Dirty_data
FROM Sales_Data
WHERE Dirty_data=1
```

### <a name="2-3">2.3. Membersihkan Kumpulan Value yang Terlalu Beragam

Salah satu cara untuk menginterpretasikan suatu set data yang meminiki value-value beragam adalah dengan melakukan standardisasi/pengelompokkan kembali. Pada contoh di bawah ini, kita akan mengelompokkan order-order berdasarkan benuanya.

```
SELECT OrderID,
       Shipping_Address,
       CASE WHEN Shipping_Address IN ('Germany','UK', 'Italy', 'Austria') THEN 'Europe'
            WHEN Shipping_Address IN ('Singapore','Japan', 'Indonesia', 'India', 'Thailand') THEN 'Asia'
            WHEN Shipping_Address IN ('Kenya','South Africa', 'Egypt') THEN 'Africa'
            ELSE 'Other'
       END AS region
FROM Sales_Data
```
  
<img src="https://user-images.githubusercontent.com/34309557/194707030-4683f303-e033-4501-a828-1506ff4bdfd7.png" width="402.25">
  
### <a name="2-4">2.4. Mengategorikan Value Sesuai dengan Interval
  
Cara untuk melakukan interpretasi pada data-data yang berbentuk numerik adalah dengan mengategorikannya berdasarkan interval. Pengategorian tersebut dapat dilakukan menggunakan statement `CASE`.

```
SELECT OrderID,
     Shipping_Cost,
     CASE WHEN Shipping_Cost < 25 THEN 'Low'
          WHEN Shipping_Cost BETWEEN 25 AND 32 THEN 'Medium'
          WHEN Shipping_Cost > 32 THEN 'High'
     END AS cost_range
FROM Sales_Data
```
  
![image](https://user-images.githubusercontent.com/34309557/194707629-c0f343d7-a728-41b5-8f8b-3e00110fd253.png)

### <a name="2-5">2.5. Membenarkan Data Type
  
Pada beberapa kasus, kita harus mengubah tipe data. Biasanya, perubahan tipe data dilakukan dari `FLOAT` ke `INT`. Untuk melakukan pengubahan tipe data, kita akan menggunakan statement `CAST` dengan format sebagai berikut.
  
`CAST(column_name AS new_data_type)`

Berikut ini adalah contoh kueri yang menggunakan statement `CASE` tersebut.

```
SELECT Shipping_Cost,
       CAST(Shipping_Cost AS REAL) AS Shipping_Cost_float
FROM Sales_Data
```
  
![image](https://user-images.githubusercontent.com/34309557/194707483-1b26f47e-f4a0-4b61-8dbd-80e5599b96f8.png)

## <a name="dp-with-python"></a>3. Data Preprocessing dengan Python

Data preprocesing menggunakan python lebih mudah dibandingkan dengan SQL karena SQL memiliki keterbatasan sintaks. Sementara itu, python memiliki banyak library yang dapat mengakomodasi data preprocessing dengan panggilan fungsi saja. Pada section ini, akan dibahas data preprocessing dengan python menggunakan library pandas. Maka dari itu, pertama-tama kita harus mengimport library terlebih dahulu.

```
#importing module
import pandas as pd
```

### <a name="3-1">3.1. Import Dataset

Sebelum melakukan preprocessing, data set harus dimport ke python terlebih dahulu. Pengimportan dilakukan dengan `read_csv(loc)` yang mana loc diisi dengan lokasi csv di workspace kita. 

![image](https://user-images.githubusercontent.com/34309557/194736072-d3c49d6e-0ff8-48e9-9225-2389a733cb7f.png)

### <a name="3-2">3.2. Mencari dan Mengisi Data Hilang

Beberapa fungsi dapat dipanggil untuk memperoleh record-record yang memiliki value null di kolom tertentu.

<b>Fungsi isnull()</b>

`data.isnull()`

![image](https://user-images.githubusercontent.com/34309557/194736111-4ade3831-afd5-451f-8c07-a1ab5926f894.png)

Fungsi tersebut mengembalikan nilai boolean pada tiap field yang menyatakan apakah field tersebut null atau tidak.

<b>Fungsi isna().any()</b>

`data.isna().any()`

![image](https://user-images.githubusercontent.com/34309557/194736191-0dc33cdd-a6e4-407c-b4ae-a02b59178600.png)

Fungsi tersebut akan mengembalikan nilai boolean pada tiap kolom yang mengindikasikan apakah kolom tersebut mempunyai value bernilai null atau tidak.

<b>Fungsi isna().sum()</b>

 `data.isna().sum()`

![image](https://user-images.githubusercontent.com/34309557/194736211-4316658c-6219-40a2-8ee8-4b2948842ba4.png)

Fungsi tersebut mengembalikan jumlah data null pada tiap kolom.

<b>Fungsi isna().any().sum()</b>

`data.isna().any().sum()`

![image](https://user-images.githubusercontent.com/34309557/194736241-f5ee6dda-f06e-47fe-aa77-918180825d5f.png)

Fungsi tersebut akan mengembalikan boolean yang mewakili adanya nilai null dalam keseluruhan tabel

<b>Fungsi fillna()</b>

`pd.fillna(value=None, method=None, axis=None, inplace=False, limit=None, downcast=None)`

Fungsi tersebut akan mengisi field yang null dengan `value`. Detil dari setiap atributnya dapat dilihat di [sini](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.fillna.html)

### <a name="3-3">3.3. Menghapus data duplikat

Untuk menampilkan data duplikat, fungsi ini dapat dipanggil.

`data.duplicated()`

Selanjutnya, untuk menghapus data duplikat, fungsi ini dipanggil.

`data.drop_duplicates(subset=None, keep='first', inplace=False, ignore_index=False)`

Detil setiap atribut bisa dibaca di [sini](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.drop_duplicates.html)

### <a name="3-4">3.4. Membersihkan format data
  
Untuk membersihkan format data dalam python, kita bisa menggunakan fungsi `where()`. Pada dasarnya, fungsi `where()` berfungsi mirip dengan if-statement.
  
![image](https://user-images.githubusercontent.com/34309557/194736607-ce2348ab-d64f-4b63-bed0-a485f4bb01bc.png)

![image](https://user-images.githubusercontent.com/34309557/194736643-4c5707be-ebcb-4115-9786-a93da63a0d7d.png)

Berikut ini adalah contoh apabila kita ingin membersihkan set data yang memiliki ragam data sebagai berikut.
  
![image](https://user-images.githubusercontent.com/34309557/194736713-2ef9395a-838a-49fa-82f2-2241f8c2bae9.png)

Pertama-tama, kita harus mengambil referensi berbentuk tabel terhadap record-record yang mengandung string `London` untuk tempat di London dan `Oxford` untuk publikasi di Oxford.
  
![image](https://user-images.githubusercontent.com/34309557/194736765-7d8c9cbe-75e8-4c7f-8459-6ffc982dcdf6.png)
  
Setelah itu, kita bisa mengganti semua data hingga menjadi London atau Oxford saja. Apabila tidak mengandung keduanya, tempat publikasi akan dibiarkan tetapi tetap akan dirapihkan dengan menggantikan semua `-` dengan spasi.
  
![image](https://user-images.githubusercontent.com/34309557/194737215-5a9141b7-3d60-4135-a2db-3e3e0464571e.png)

### <a name="3-5">3.5. Export Dataset

Set data yang sudah dilakukan preprocessing dapat di-export dengan menggunakan sintaks sebagai berikut

`data.to_csv('hasil.csv')`

## <a name="referensi"></a>Latihan

1. Silahkan download data set [berikut.](https://github.com/Manajemen-Cerdas-Informasi/Modul-LBE-2022/blob/main/modul-sql/data-preprocessing/file/hotel_boookings.csv) Kerjakan menggunakan BigQuery dengan pertama-tama mengimport csv untuk langsung digenerate sebagai tabel pada suatu set data. Setelah itu, lakukan preprocessing dengan SQL sehingga menghasilkan tabel `hotel_bookings` sebagai berikut.
   - Hapus semua data yang bookingnya dicancel
   - Jadikan tipe data `adults` dan `lead_time` integer
   - Hapus kolom is_repeated dan previous_bookings
   - Lakukan select yang menunjukkan reservasi eksekutif (A, B), bisnis (C, D, E) dan ekonomi (F, G, H).
  
## <a name="referensi"></a>Referensi

- https://www.analyticsvidhya.com/blog/2021/06/data-cleaning-using-pandas/
- https://towardsdatascience.com/5-easy-sql-tricks-to-clean-dirty-data-dc423a0ab3e9
- https://realpython.com/python-data-cleaning-numpy-pandas/
