# LBE MCI 2022 - Libraries Python

- [Pendahuluan](#pendahuluan)
  - [Dataset](#dataset)
  - [Text Editor](#text_editor)
- [Pandas](#pandas)
  - [Import Pandas](#import_pandas)
  - [Membaca File CSV](#membaca_file_csv)
  - [Sample Data Pandas](#sample_data_pandas)
    - [Head()](#head)
    - [Tail()](#tail)
    - [Sample()](#sample)
  - [Jumlah Data](#jumlah_data)
    - [Count()](#count)
    - [Shape[]](#shape_siku)
  - [Informasi Struktur Data](#informasi_struktur_data)
    - [Shape](#shape)
    - [Dtypes](#dtypes)
    - [Info()](#info)
  - [Informasi Statistik](#informasi_statistik)
- [Referensi](#referensi)

</br>

# <a name="pendahuluan"></a>Pendahuluan

Library python adalah kumpulan modul terkait berisi kumpulan kode yang dapat digunakan berulang kali dalam program yang berbeda. Library juga berguna untuk mengolah dataset agar data bisa menjadi informasi yang berguna dan bisa digunakan.

## <a name="dataset"></a>Dataset

Pada kali ini, kita akan menggunakan dataset yang mudah dan tidak mengandung data yang terlalu banyak supaya lebih fokus kepada penggunaan library python itu sendiri. Adapun dataset yang dipakai yaitu Vaksinasi Negara Republik Indonesia yang bisa kalian akses pada link berikut

> <a href="https://raw.githubusercontent.com/owid/covid-19-data/master/public/data/vaccinations/country_data/Indonesia.csv">Data Vaksinasi Indonesia</a>

Dataset yang digunakan berisikan kolom _locations_, _date_, _vaccine_, dan _source-url_.

## <a name="text_editor"></a>Text Editor

Selanjutnya kita bisa mengunakan text editor apa aja yang ingin digunakan misalnya Google Collaboratory, Jupyter Notebook, Anaconda, Visual Studio Code, Terminal Python, dan lain-lain. Pada kali ini, kita akan mencobanya di `Visual Studio Code`. Langkah pertama, ketikkan command berikut untuk memperbarui versi python pada terminal komputer.

```
pip3 install --upgrade pip
```

# <a name="pandas"></a>Pandas

Pandas adalah sebuah paket library pada python yang digunakan untuk mempermudah dalam mengolah dan menganalisa data-data terstruktur. Pandas merupakan paket penting yang wajib diketahui untuk seorang data engineer, data analyst dan data scientist jika ingin mengolah dan menganalisa data menggunakan python.

</br>

Pandas memiliki format data yang sering digunakan yang disebut `DataFrame`. `Pandas DataFrame` adalah struktur data 2 Dimensi. Data distrukturisasi seperti tabel yang berisi baris dan kolom, sehingga mudah untuk melakukan queri atau mengakses data tersebut. Baris merepresentasikan **record** dan kolom merepresentasikan **field**.

## <a name="import_pandas"></a>Import Pandas

Pada terminal, tuliskan command berikut untuk mendowload library pandas ke komputer kita.

```
pip3 install pandas
```

Untuk menggunakan Pandas maka harus melakukan import dan bisa kita memberikan nama yang lebih pendek agar lebih mudah digunakan contohnya `pd` sehingga jika dituliskan dalam program python menjadi

```
import pandas as pd
print('Pandas version: {}'.format(pd.__version__))
```

maka akan keluar hasil versi dari pandas tersebut </br>
<img src="https://user-images.githubusercontent.com/70510279/193408374-a129cc68-8650-4df5-bb3c-2c4dc38ec05b.png" alt="Import Pandas" width="1000"/>

## <a name="membaca_file_csv"></a>Membaca File CSV

Cara membaca isi file dengan format csv menggunakan python yaitu sebagai berikut

```
url = "https://raw.githubusercontent.com/owid/covid-19-data/master/public/data/vaccinations/country_data/Indonesia.csv"
df = pd.read_csv(url, index_col=0)
```

> Catatan: URL yang digunakan yaitu URL dari file CSV yang ingin kita akses

## <a name="sample_data_pandas"></a>Sample Data Pandas

Setelah berhasil diload ke dalam Pandas DataFrame, maka kita menggunakan fungsi supaya bisa melihat data sampel di dataset.

```
df
```

### <a name="head"></a>Head()

Fungsi `head()` pada sample data Pandas digunakan untuk melihat `n-record` baris pertama pada DataFrame.

```
df.head()
```

### <a name="tail"></a>Tail()

Fungsi `tail()` pada sample data Pandas digunakan untuk melihat `n-record` baris terakhir pada DataFrame.

```
df.tail()
```

### <a name="sample"></a>Sample()

Fungsi `sample()` pada sample data Pandas digunakan untuk melihat `n-record` secara acak pada DataFrame.

```
df.sample()
```

## <a name="jumlah_data"></a>Jumlah Data

Menggunakan library Pandas, kita juga bisa melihat jumlah data yang ada pada dataset yang kita gunakan. Berikut cara memperoleh jumlah data menggunakan Pandas:

### <a name="count"></a>Count()

Untuk memperoleh informasi jumlah records pada setiap kolom maka bisa menggunakan `count()`.

```
df.count()
```

### <a name="shape_siku"></a>Shape[0]

Cara lain untuk menampilkan jumlah records pada setiap bisa menggunakan `shape[0]`.

```
df.shape[0]
```

## <a name="informasi_struktur_data"></a>Informasi Struktur Data

### <a name="shape"></a>Shape

Untuk mengetahui dimensi dari suatu dataframe bisa menggunakan `df.shape`. Hasilnya yaitu `(p1, p2)`, pada property pertama akan bernilai jumlah baris/record dalam dataframe dan pada property kedua akan bernilai jumlah kolom dalam dataframe.

```
df.shape
```

### <a name="dtypes"></a>Dtypes

Fungsi `df.dtypes` digunakan untuk melihat struktur dari data di setiap kolomnya. Berikut cara penggunaannya

```
df.dtypes
```

### <a name="info"></a>Info()

Untuk mengetahui lebih detail mengenai struktur DataFrame bisa menggunakan `df.info`

```
df.info()
```

## <a name="informasi_statistik"></a>Informasi Statistik

Informasi statistik untuk setiap kolom seperti nilai minimum, nilai maksimum, standar deviasi, rata-rata dan sebagainya, dapat ditampilkan dengan mengikuti perintah berikut

```
df.describe(include='all')
```

# <a name="referensi"></a>Referensi

- https://hub.idbigdata.com/sigit-prasetyo/panduan-praktis-penggunaan-pandas-bagian-1-39
