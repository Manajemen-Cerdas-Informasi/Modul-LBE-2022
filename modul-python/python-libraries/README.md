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
  - [Menampilkan Kolom](#menampilkan_kolom)
  - [Filtering Data](#filtering_data)
  - [Sort Data](#sort_data)
  - [Agregasi Data](#agregasi_data)
- [Numpy](#numpy)
  - [Array NumPy](#array_numpy)
    - [Zeros()](#array_zeros)
    - [Ones()](#array_ones)
    - [Arange()](#array_arange)
    - [Linspace()](#array_linspace)
    - [Longspace()](#array_longspace)
  - [Multidimensional Array](#multidimensional_array)
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
df = pd.read_csv(url, index_col=0)
```

Adapun jika menggunakan dataset yang kita gunakan yaitu sebagai berikut

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

## <a name="menampilkan_kolom"></a>Menampilkan Kolom

Penggunaan Pandas juga bisa dilakukan untuk menampilkan data berdasarkan nama kolom yg diinginkan.

```
df[['kolom1', 'kolom2']].head()
```

## <a name="filtering_data"></a>Filtering Data

Salah satu bagian penting yang digunakan dalam penyiapan data dan analisis data adalah filtering, yaitu pemilihan data dengan kriteria tertentu. Ini juga disebut data subset. Format filtering adalah sebagai berikut

```
df[(df.key == "value")]
```

Contoh sesuai dataset, jika kita ingin memfilter data vaksin yang menggunakan bersumber dengan url `https://covid19.who.int/` adalah sebagai berikut

```
df[(df.source_url == "https://covid19.who.int/")]
```

## <a name="sort_data"></a>Sort Data

Fungsi `sort_values()` digunakan untuk melakukan pengurutan data berdasarkan dengan kolom yang disebutkan mulai dari nilai terkecil.

```
df.sort_values('kolom')
```

Jika ingin mengurutkan data dimulai dari nilai terbesar yaitu dengan mengubah nilai `ascending = FALSE`.

```
df.sort_values('kolom', ascending = False)
```

## <a name="agregasi_data"></a>Agregasi Data

Pandas menyediakan fungsi statistik agregasi, seperti count, sum, min, max dan lainnya. Fungsi-fungsi ini dapat diterapkan ke kolom.

```
df.sum()
df.min()
df.max()
df.mean()
```

Adapun jika ingin menghitung berdasarkan kolomnya maka bisa dilakukan sebagai berikut

```
df.kolom.sum()
```

# <a name="numpy"></a>Numpy

NumPy merupakan salah satu library Python yang banyak digunakan dalam proses analisis data karena fiturnya yang hebat. NumPy hampir menyerupai List pada Python tetapi lebih powerful. Ada beberap kelebihan NumPy dibandingkan List seperti size, performance dan functionally. Struktur data NumPy lebih membutuhkan ukuran yang lebih kecil dibandingkan dengan List tetapi mempunyai performa yang lebih cepat.

Pada terminal, tuliskan command berikut untuk mendowload library NumPy ke komputer kita.

```
pip install numpy
```

ntuk menggunakan NumPy maka harus melakukan import dan bisa kita memberikan nama yang lebih pendek agar lebih mudah digunakan contohnya `np` sehingga jika dituliskan dalam program python menjadi

```
import numpy as np
```

## <a name="array_numpy"></a>Array NumPy

Kita bisa membuat Array menggunakan NumPy dengan membungkusnya terlebih dahulu di List dan dirubah menjadi numpy array.

```
np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
```

### <a name="array_zeros"></a>Zeros()

Membuat array dengan nilai 0

```
np.zeros(n)
```

### <a name="array_ones"></a>Ones()

Membuat array dengan nilai 1

```
np.ones(n)
```

### <a name="array_arange"></a>Arange()

Membuat array dengan nilai dalam range

```
np.arange(x, y, z)  # x = start, y = end, z = step
```

### <a name="array_linspace"></a>Linspace()

Membuat array dengan nilai dalam interval

```
np.linspace(x, y, z) # x = start, y = end, z = number
```

### <a name="array_longspace"></a>Longspace()

Membuat array dengan nilai log10 dalam interval

```
np.longspace(x, y, z) # x = start, y = end, z = number
```

## <a name="multidimensional_array"></a>Multidimensional Array

Fitur menarik dari NumPy adalah mampu membuat multidimensional array dan melakukan manipulasi array dengan mudah dan cepat. Berikut contoh array 2 dimensi yang dibuat dengan NumPy

```
np.array([[1, 2, 3, 4, 5], [6, 7, 8, 9, 10]])
```

# <a name="referensi"></a>Referensi

- https://hub.idbigdata.com/sigit-prasetyo/panduan-praktis-penggunaan-pandas-bagian-1-39
- https://hub.idbigdata.com/sigit-prasetyo/panduan-praktis-penggunaan-pandas-bagian-2-40
- https://ngodingdata.com/tutorial-dasar-numpy-python/
