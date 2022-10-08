# Modul 2 LBE MCI 2022: Database & SQL

- [Data Preprocessing](#data-preprocessing)
  - [Definisi](#definisi)
  - [Keuntungan](#keuntungan)
- [Data Preprocessing with SQL](#dp-with-SQL)
  - [Tentang](#tentang-sql)
- [Referensi](#referensi)

## <a name="data-preprocessing"></a>1. Data Preprocessing

### <a name="definisi">Apa itu data preprocessing?

Dalam dunia nyata, programmer akan banyak menemukan set data yang bersifat kotor. Set data yang bersifat kotor adalah set data yang ditulis dengan format yang tidak seragam, tidak memiliki tipe data yang sesuai, memiliki banyak field yang kosong ataupun terkorupsi. Hal ini akan menjadikan set-set data tersebut sulit untuk diinterpretasikan, divisualisasikan ataupun diproses dengan business intelligence untuk keperluan-keperluan tertentu.

<b>Data preprocessing</b> atau data cleaning adalah proses manipulasi, penghapusan, penggantian atau penambalan data kepada set data sehingga set data dapat mengakomodasi pemrosesan data lebiih lanjut. Selain itu, data preprocessing juga memiliki peran penting dalam menyiapkan data-data yang dapat diandalkan dengan menerapkan proses analitik yang sesuai dengan ilmu atau teori yang ada kepada set data yang bersifat kotor.

### <a name="keuntungan">Keuntungan dari data preprocessing

Data preprocessing memiliki banyak keuntungan. Beberapa poin penting dalam kelebihan data preprocessing adalah sebagai berikut

<b>1. Error-Free Data</b>

Ketika set data terdiri dari kumpulan data yang berasal dari sumber yang berbeda, akan terdapat kemungkinan format data pada tiap kolom berbeda dengan satu sama lainnya. Hal ini akan mengakibatkan eror apabila data set tersebut ingin diproses atau divisualisasikan karena komputer hanya dapat menerima kumpulan data dalam satu kolom dengan pemformatan yang seragam.

<b>2. Data Quality</b>

Terkadang, suatu kolom pada set data harus mengikuti aturan yang sesuai dengan keperluan. Seperti data dengan tipe data boolean yang hanya boleh memiliki nilai 0 dan 1 ataupun alamat email yang harus memiliki simbol @ atau . diantaranya. Ada beberapa kasus yang mana pengguna dapat memasukkan data yang tidak sesuai dengan constraints atau aturan-aturan tersebut.

<b>3. Accurate and Efficient</b>

Permasalahan ril membutuhkan back-up data yang juga bersifat ril. Maka dari itu, suatu set data juga harus memiliki nilai-nilai yang benar. Hal ini dapat dilakukan dengan menghapus record data yang memiliki field-field kosong atau memiliki field data yang tidak berkualitas sehingga data dari record tersebut tidak mempengaruhi hasil interpretasi atau visualisasi data.

<b>4. Complete Data</b>

Pada keadaan tertenru, untuk dapat memroses suatu set data, set data tersebut harus bersifat komplit. Seperti pada set data yang memiliki keperluan untuk mengontak orang yang terdaftar, maka field untuk nomor telepon tidak boleh kosong. Maka dari itu, data preprocessing juga mengandung proses untuk melengkapi  data, baik dilakukan secara manual (mengontak orang yang bersangkutan/mengadakan pengisian form kembali) ataupun dilakukan secara otomatis oleh suatu intelligent system.

<b>5. Maintains Data Consistency</b>

Untuk memastikan bahwa suatu record bersifat konsisten, kita dapat melakukan komparasi suatu record dengan konteks ataupun dengan record lainnya. Seperti contoh, apabila kita memiliki suatu record yang menyatakan bahwa baju dengan harga `Rp10.000` berada di kategori `Mahal`, kita perlu melakukan cross-check kepada record lain dan melihat apakah memang baju `Rp10.000` dikategorikan sebagai `Mahal` dalam set data tersebut. Apabila tidak, kita harus melakukan preprocessing dan memanipulasi data tersebut supaya menjadi benar dan konsisten.

## <a name="dp-with-SQL"></a>2. Data Preprocessing with SQL

Data preprocessing dapat dilakukan dengan banyak cara, baik menggunakan python, SQL, pendekatan manual (mengadakan kuesioner kembali) ataupun dengan tools lainnya yang dapat membersihkan set data. Pada kesempatan kali ini, kita akan belajar data preprocessing dengan SQL.

<b>1. Mencari record dengan values yang hilang</b>

Cara mencari record yang memiliki nilai null pada suatu field adalah dengan menggunakan sintaks `WHERE <field> IS NULL`. Berikut ini adalah contoh penggunaannya.

```
SELECT OrderID,
       Sales_Manager,
       Product_Category,
       Shipping_Address
FROM Dummy_Sales_Data_v1
WHERE Product_Category IS NULL
```

![image](https://user-images.githubusercontent.com/34309557/194705315-a3915fa7-d2c3-4116-a2a2-29901f2d95f1.png)






## <a name="referensi"></a>Referensi

- https://www.analyticsvidhya.com/blog/2021/06/data-cleaning-using-pandas/
- https://towardsdatascience.com/5-easy-sql-tricks-to-clean-dirty-data-dc423a0ab3e9
