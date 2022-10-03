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
  - [Import Numpy](#import_numpy)
  - [Array NumPy](#array_numpy)
    - [Zeros()](#array_zeros)
    - [Ones()](#array_ones)
    - [Arange()](#array_arange)
    - [Linspace()](#array_linspace)
    - [Longspace()](#array_longspace)
  - [Multidimensional Array](#multidimensional_array)
  - [Indexing](#indexing)
  - [Fungsi Statistik](#fungsi_statistik)
- [Matplotlib](#matplotlib)
  - [Import Matplotlib](#import_matplotlib)
  - [Grafik Sederhana](#grafik_sederhana)
  - [Histogram](#histogram)
  - [Scatter Plot](#scatter_plot)
  - [Bar Plot](#bar_plot)
  - [Pie Chart](#pie_chart)
  - [Stacked Bar Plot](#stacked_bar)
  - [Stacked Area Plot](#stacked_area)
  - [Multiple Line](#multiple_line)
  - [Multiple Bar](#multiple_bar)
- [Seaborn](#seaborn)
  - [Import Seaborn](#import_seaborn)
  - [Scatter Plot](#seaborn_scatter)
  - [Bar Plot](#seaborn_bar)
  - [Line Plot](#seaborn_line)
  - [Box Plot](#seaborn_box)
  - [Distribution Plot](#seaborn_dist)
  - [Heatmap](#seaborn_heatmap)
- [Referensi](#referensi)

</br>

# <a name="pendahuluan"></a>Pendahuluan

*Library* Python adalah kumpulan modul terkait berisi kumpulan kode yang dapat digunakan berulang kali dalam program yang berbeda. *Library* juga berguna untuk mengolah dataset agar data bisa menjadi informasi yang berguna dan bisa digunakan.

## <a name="dataset"></a>Dataset

Pada kali ini, kita akan menggunakan dataset yang mudah dan tidak mengandung data yang terlalu banyak supaya lebih fokus kepada penggunaan *library* Python itu sendiri. Adapun dataset yang dipakai yaitu Vaksinasi Negara Republik Indonesia yang bisa kalian akses pada *link* berikut:

> <a href="https://raw.githubusercontent.com/owid/covid-19-data/master/public/data/vaccinations/country_data/Indonesia.csv">Data Vaksinasi Indonesia</a>

Dataset yang digunakan berisikan kolom _locations_, _date_, _vaccine_, dan _source-url_.

## <a name="text_editor"></a>Text Editor

Selanjutnya kita bisa mengunakan *text editor* apa saja yang ingin digunakan misalnya Google Colaboratory, Jupyter Notebook, Anaconda, Visual Studio Code, Terminal Python, dan lain-lain. Pada kali ini, kita akan mencobanya di `Visual Studio Code`. Langkah pertama, ketikkan *command* berikut untuk memperbarui versi Python pada terminal komputer.

```
pip3 install --upgrade pip
```

Setelah itu, bisa dilanjutkan dengan meng-*install* *extension* `Jupyter` pada Visual Studio Code. Setelah itu, buatlah *file* baru dengan ekstensi `.ipynb` dan bisa langsung kita mulai.

# <a name="pandas"></a>Pandas

Pandas adalah sebuah paket *library* pada Python yang digunakan untuk mempermudah dalam mengolah dan menganalisa data-data terstruktur. Pandas merupakan paket penting yang wajib diketahui untuk seorang *data engineer*, *data analyst*, dan *data scientist* jika ingin mengolah dan menganalisa data menggunakan Python.

</br>

Pandas memiliki format data yang sering digunakan yang disebut `DataFrame`. `Pandas DataFrame` adalah struktur data 2 dimensi. Data distrukturisasi seperti tabel yang berisi baris dan kolom, sehingga mudah untuk melakukan *query* atau mengakses data tersebut. Baris merepresentasikan **record** dan kolom merepresentasikan **field**.

## <a name="import_pandas"></a>Import Pandas

Pada terminal, tuliskan *command* berikut untuk men-*download* *library* Pandas ke komputer kita.

```
pip3 install pandas
```

Untuk menggunakan Pandas, maka harus melakukan *import* dan bisa kita memberikan nama yang lebih pendek agar lebih mudah digunakan contohnya `pd` sehingga jika dituliskan dalam program Python menjadi:

```python
import pandas as pd
print('Pandas version: {}'.format(pd.__version__))
```

Maka akan keluar hasil versi dari pandas tersebut </br>
<img src="https://user-images.githubusercontent.com/70510279/193408374-a129cc68-8650-4df5-bb3c-2c4dc38ec05b.png" alt="Import Pandas" width="1000"/>

## <a name="membaca_file_csv"></a>Membaca File CSV

Cara membaca isi *file* dengan format CSV menggunakan Python yaitu sebagai berikut:

```python
df = pd.read_csv(url, index_col=0)
```

Adapun jika menggunakan dataset yang kita gunakan yaitu sebagai berikut:

```python
url = "https://raw.githubusercontent.com/owid/covid-19-data/master/public/data/vaccinations/country_data/Indonesia.csv"
df = pd.read_csv(url, index_col=0)
```

> Catatan: URL yang digunakan yaitu URL dari file CSV yang ingin kita akses.

## <a name="sample_data_pandas"></a>Sample Data Pandas

Setelah berhasil di-*load* ke dalam Pandas DataFrame, maka kita menggunakan fungsi supaya bisa melihat data sampel di dataset.

```python
df
```

Hasilnya akan seperti ini: </br>
<img src="https://user-images.githubusercontent.com/70510279/193499215-d999c771-0e8e-4027-be92-7ab598e2dca1.png" alt="Sample Data Pandas" width="1000"/>

### <a name="head"></a>Head()

Fungsi `head()` pada sampel data Pandas digunakan untuk melihat `n-record` baris pertama pada DataFrame.

```python
df.head()
```

Hasilnya yaitu: </br>
<img src="https://user-images.githubusercontent.com/70510279/193498137-29896a78-3152-47b0-b6cc-71f8074fda09.png" alt="Head Pandas" width="1000"/>

### <a name="tail"></a>Tail()

Fungsi `tail()` pada sampel data Pandas digunakan untuk melihat `n-record` baris terakhir pada DataFrame.

```python
df.tail()
```

Hasilnya yaitu </br>
<img src="https://user-images.githubusercontent.com/70510279/193498267-09e81c14-841b-4276-8c2c-3b1d9763e86b.png" alt="Tail Pandas" width="1000"/>

### <a name="sample"></a>Sample()

Fungsi `sample()` pada sampel data Pandas digunakan untuk melihat `n-record` secara acak pada DataFrame.

```python
df.sample()
```

Hasilnya yaitu: </br>
<img src="https://user-images.githubusercontent.com/70510279/193498399-8e913e8c-0441-415c-9005-1254b6c98695.png" alt="Sample Pandas" width="1000">

## <a name="jumlah_data"></a>Jumlah Data

Menggunakan *library* Pandas, kita juga bisa melihat jumlah data yang ada pada dataset yang kita gunakan. Berikut cara memperoleh jumlah data menggunakan Pandas:

### <a name="count"></a>Count()

Untuk memperoleh informasi jumlah *record* pada setiap kolom, maka bisa menggunakan `count()`.

```python
df.count()
```

Hasilnya yaitu: </br>
<img src="https://user-images.githubusercontent.com/70510279/193498614-ce57a7d9-7a8a-46f5-b323-c2367315086e.png" alt="Count Pandas" width="200"/>

### <a name="shape_siku"></a>Shape[0]

Cara lain untuk menampilkan jumlah *record* pada setiap bisa menggunakan `shape[0]`.

```python
df.shape[0]
```

Hasilnya yaitu: </br>
<img src="https://user-images.githubusercontent.com/70510279/193498839-e39d1a32-db7b-4581-9e3e-a260ee2215ea.png" alt="Shape Pandas" width="200"/>

## <a name="informasi_struktur_data"></a>Informasi Struktur Data

### <a name="shape"></a>Shape

Untuk mengetahui dimensi dari suatu DataFrame bisa menggunakan `df.shape`. Hasilnya yaitu `(p1, p2)`, pada *property* pertama akan bernilai jumlah baris/*record* dalam DataFrame dan pada *property* kedua akan bernilai jumlah kolom dalam DataFrame.

```python
df.shape
```

Hasilnya yaitu </br>
<img src="https://user-images.githubusercontent.com/70510279/193498976-c77e9369-3c88-49c5-8d28-396da9a83b4b.png" alt="Shape Pandas" width="100"/>

### <a name="dtypes"></a>Dtypes

Fungsi `df.dtypes` digunakan untuk melihat struktur dari data di setiap kolomnya. Berikut cara penggunaannya:

```python
df.dtypes
```

Maka akan keluar hasil seperti ini </br>
<img src="https://user-images.githubusercontent.com/70510279/193499319-995f7475-2b58-4748-8aec-b64c7202b06b.png" alt="Dtypes Pandas" width="300"/>

### <a name="info"></a>Info()

Untuk mengetahui lebih detail mengenai struktur DataFrame bisa menggunakan `df.info`.

```python
df.info()
```

Hasilnya yaitu: </br>
<img src="https://user-images.githubusercontent.com/70510279/193499832-23de59ef-9ebe-47fa-9d8d-cc08641a9165.png" alt="Info Pandas" width="300"/>

## <a name="informasi_statistik"></a>Informasi Statistik

Informasi statistik untuk setiap kolom seperti nilai minimum, nilai maksimum, standar deviasi, rata-rata dan sebagainya, dapat ditampilkan dengan mengikuti perintah berikut:

```python
df.describe(include='all')
```

Hasilnya yaitu: </br>
<img src="https://user-images.githubusercontent.com/70510279/193499927-9f8f6be6-0490-4f60-81da-bf27f67cff0f.png" alt="Describe Pandas" width="1000"/>

## <a name="menampilkan_kolom"></a>Menampilkan Kolom

Penggunaan Pandas juga bisa dilakukan untuk menampilkan data berdasarkan nama kolom yg diinginkan.

```python
df[['kolom1', 'kolom2']].head()
```

Jika menggunakan dataset yang sudah di-*load* sebelumnya, maka hasilnya akan seperti ini </br>
<img src="https://user-images.githubusercontent.com/70510279/193500130-441c9f85-a375-4672-8ded-dc6315399c95.png" alt="Menampilkan Kolom Pandas" width="500"/>

## <a name="filtering_data"></a>Filtering Data

Salah satu bagian penting yang digunakan dalam penyiapan data dan analisis data adalah *filtering*, yaitu pemilihan data dengan kriteria tertentu. Ini juga disebut data subset. Format *filtering* adalah sebagai berikut:

```python
df[(df.key == "value")]
```

Contoh sesuai dataset, jika kita ingin mem-*filter* data vaksin yang menggunakan sumber `https://covid19.who.int/` adalah sebagai berikut:

```python
df[(df.source_url == "https://covid19.who.int/")]
```

<img src="https://user-images.githubusercontent.com/70510279/193501786-06306bab-2ef3-4843-96c0-80711b2308db.png" alt="Filtering Data Pandas" width="1000"/>

## <a name="sort_data"></a>Sort Data

Fungsi `sort_values()` digunakan untuk melakukan pengurutan data berdasarkan dengan kolom yang disebutkan mulai dari nilai terkecil.

```python
df.sort_values('kolom')
```

Jika ingin mengurutkan data dimulai dari nilai terbesar yaitu dengan mengubah nilai `ascending = FALSE`.

```python
df.sort_values('kolom', ascending = False)
```

Jika menggunakan dataset yang sudah di load sebelumnya, maka hasilnya akan seperti ini </br>
<img src="https://user-images.githubusercontent.com/70510279/193502033-586a4730-41c5-4be2-8c31-d117daf83c06.png" alt="Sort Data Pandas" width="1000"/>

## <a name="agregasi_data"></a>Agregasi Data

Pandas menyediakan fungsi statistik agregasi, seperti `count`, `sum`, `min`, `max` dan lainnya. Fungsi-fungsi ini dapat diterapkan ke kolom.

```python
df.sum()
df.min()
df.max()
df.mean()
```

Adapun jika ingin menghitung berdasarkan kolomnya maka bisa dilakukan sebagai berikut

```python
df.kolom.sum()
```

# <a name="numpy"></a>NumPy

NumPy merupakan salah satu *library* Python yang banyak digunakan dalam proses analisis data karena fiturnya yang hebat. NumPy hampir menyerupai *list* pada Python tetapi lebih *powerful*. Ada beberapa kelebihan NumPy dibandingkan *list* seperti *size*, *performance* dan *functionally*. Struktur data NumPy lebih membutuhkan ukuran yang lebih kecil dibandingkan dengan *list* tetapi mempunyai performa yang lebih cepat.

## <a name="import_numpy"></a>Import NumPy

Pada terminal, tuliskan *command* berikut untuk men-*download* *library* NumPy ke komputer kita.

```
pip install numpy
```

Untuk menggunakan NumPy, maka harus melakukan *import* dan bisa kita memberikan nama yang lebih pendek agar lebih mudah digunakan contohnya `np` sehingga jika dituliskan dalam program Python menjadi:

```python
import numpy as np
```

## <a name="array_numpy"></a>Array NumPy

Kita bisa membuat *array* menggunakan NumPy dengan membungkusnya terlebih dahulu di *list* dan dirubah menjadi *array* NumPy.

```python
np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
```

<img src="https://user-images.githubusercontent.com/70510279/193502179-d8098475-3927-4292-b2ec-e378c7c44453.png" alt="Array NumPy" width="400"/>

### <a name="array_zeros"></a>Zeros()

Membuat *array* dengan nilai 0.

```python
np.zeros(n)
```

<img src="https://user-images.githubusercontent.com/70510279/193502238-187e1f35-f925-4036-b570-dd8a77cf0405.png" alt="Array NumPy" width="300"/>

### <a name="array_ones"></a>Ones()

Membuat *array* dengan nilai 1.

```python
np.ones(n)
```

<img src="https://user-images.githubusercontent.com/70510279/193502548-1a3b94e0-562f-494e-b1f4-4b1404e0382f.png" alt="Array NumPy" width="300"/>

### <a name="array_arange"></a>Arange()

Membuat *array* dengan nilai dalam *range*.

```python
np.arange(x, y, z)  # x = start, y = end, z = step
```

<img src="https://user-images.githubusercontent.com/70510279/193502725-5a86d61b-8b66-42a1-a3d6-f93ed1513f4a.png" alt="Array NumPy" width="500"/>

### <a name="array_linspace"></a>Linspace()

Membuat *array* dengan nilai dalam interval.

```python
np.linspace(x, y, z) # x = start, y = end, z = number
```

<img src="https://user-images.githubusercontent.com/70510279/193502832-af454977-0aa6-4fa0-944d-8a314cd3f93d.png" alt="Array NumPy" width="500"/>

### <a name="array_longspace"></a>Longspace()

Membuat *array* dengan nilai log10 dalam interval.

```python
np.longspace(x, y, z) # x = start, y = end, z = number
```

## <a name="multidimensional_array"></a>Multidimensional Array

Fitur menarik dari NumPy adalah mampu membuat *array* multidimensional dan melakukan manipulasi *array* dengan mudah dan cepat. Berikut contoh *array* 2 dimensi yang dibuat dengan NumPy:

```python
np.array([[1, 2, 3, 4, 5], [6, 7, 8, 9, 10]])
```

<img src="https://user-images.githubusercontent.com/70510279/193502948-5382374b-bd9d-4439-b339-e0e11aad2fe2.png" alt="Multidimensional Array" width="200"/>

## <a name="indexing"></a>Indexing

Dengan NumPy, kita juga bisa melakukan _indexing_ dan _slicing_ array dengan mudah. *Indexing* pada *array* dimulai dari 0 dan dengan notasi *brackets* `[]`.

```python
array_baru = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

array_baru[0]     # 1
array_baru[0:4]   # [1, 2, 3, 4]
```

## <a name="aritmetika"></a>Aritmatika

Dengan menggunakan NumPy, kita bisa melakukan operasi seperti penjumlahan, pengurangan, perkalian, pembagian, dan lainnya. Berikut contoh operasi aritmetika pada array.

```python
arr_A = np.array([1,2,3,4,5])
arr_B = np.array([2,2,2,2,2])

print("Penjumlahan = ", arr_A + arr_B)
print("Pengurangan = ", arr_A - arr_B)
print("Perkalian = ", arr_A * arr_B)
print("Pembagian = ", arr_A / arr_B)
print("Perpangkatan = ", arr_A ** arr_B)
```

<img src="https://user-images.githubusercontent.com/70510279/193508484-739c2753-9e67-472f-b9ec-5b59fd24645d.png" alt="Aritmetika" width="300"/>

## <a name="fungsi_statistik"></a>Fungsi Statistik

NumPy bisa melakukan fungsi statistik seperti menghitung nilai minimal, maksimal, rata-rata, penjumlahan, dan lainnya. Berikut contoh penggunaan fungsi statistik pada *array*.

```python
arr = np.array([1,2,3,4,5])

print("Nilai minimal = ", arrku.min())
print("Nilai maksimal = ", arrku.max())
print("Nilai rata-rata = ", arrku.mean())
print("Total nilai = ", arrku.sum())
print("Standar Deviasi = ", arrku.std())
```

<img src="https://user-images.githubusercontent.com/70510279/193508827-9e95508e-ddfa-48e3-a2de-d5e4aa15b7a9.png" alt="Fungsi Statistik" width="300"/>

# <a name="matplotlib"></a>Matplotlib

Visualisasi data merupakan salah satu hal penting untuk mempermudah memahami data. Dalam Python kita bisa dengan mudah melakukan visualisasi data dengan *library* Matplotlib. `matplotlib.pyplot` adalah kumpulan fungsi yang membuat beberapa perubahan pada gambar, misalnya membuat gambar, membuat area plot dalam gambar, menambah label di plot, dan lainnya.

## <a name="import_matplotlib"></a>Import Matplotlib

Pada terminal, tuliskan *command* berikut untuk men-*dowload* *library* Matplotlib ke komputer kita.

```
pip install matplotlib
```

Untuk menggunakan Matplotlib maka harus melakukan *import* dan bisa kita memberikan nama yang lebih pendek agar lebih mudah digunakan contohnya `plt` sehingga jika dituliskan dalam program Python menjadi:

```python
import matplotlib.pyplot as plt
```

## <a name="grafik_sederhana"></a>Grafik Sederhana

Jika ingin membuat grafik sederhana, kita bisa menggunakan fungsi `plot()` dan `show()`. Berikut contoh membuat grafik sederhana dengan Matplotlib.

```python
plt.plot([1, 2, 3, 4, 5], [1, 4, 9, 16, 25])
plt.show()
```

Kita juga bisa menambahkan label pada grafik yang telah dibuat yaitu sebagai berikut:

```python
plt.plot([1, 2, 3, 4, 5], [1, 4, 9, 16, 25])

plt.ylabel('label Y')
plt.xlabel('label X')

plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193509366-0d4f4323-e808-4c4a-87d8-295734c063a6.png" alt="Grafik Sederhana" width="300"/>

## <a name="histogram"></a>Histogram

Histogram adalah bentuk grafik yang menyatakan tabulasi frekuensi dalam bentuk batang. Histogram memudahkan kita untuk memahami ringkasan persebaran data. Berikut contoh membuat histogram dengan Matplotlib yaitu dengan fungsi `hist()`.

```python
x = np.random.normal(170, 10, 250) # np adalah library NumPy
plt.hist(x)
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193509563-31ba62a8-3d7f-4ff7-aba3-127d733bb269.png" alt="Histogram" width="300"/>

## <a name="scatter_plot"></a>Scatter Plot

Dengan menggunakan Matplotlib kita juga bisa membuat *scatter plot*. *Scatter plot* adalah grafik yang menampilkan hubungan antara dua variabel. Berikut contoh membuat *scatter plot* dengan Matplotlib.

```python
arr_A = np.array([3, 5, 7, 9, 11, 16, 18, 20, 22, 24])
arr_B = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

plt.scatter(arr_A, arr_B)
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193510712-5670f2ad-2179-4059-801f-a564348c5834.png" alt="Scatter Plot" width="300"/>

Kita juga bisa membandingkan dua buah *scatter plot* contohnya adalah sebagai berikut

```python
arr_A = np.array([3, 5, 7, 9, 11, 16, 18, 20, 22, 24])
arr_B = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
plt.scatter(arr_A, arr_B, color='r')

arr_C = np.array([4, 6, 8, 10, 12, 17, 19, 21, 23, 25])
arr_D = np.array([1, 3, 5, 7, 9, 11, 13, 15, 17, 19])
plt.scatter(arr_C, arr_D, color='b')
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193510811-971a4a44-1d87-4d0f-93ce-4c580d4af9a3.png" alt="Scatter Plot" width="300"/>

## <a name="bar_plot"></a>Bar Plot

*Bar plot* atau *bar chart* adalah jenis plot yang direpresentasikan dengan bar atau batang, ketika panjang bar adalah representasi dari ukuran sebuah fitur atau variabel. Berikut contoh membuat *bar plot* dengan Matplotlib.

```python
matkul = ['dasprog', 'strukdat', 'pweb', 'pbo', 'paa', 'sbd', 'mbd']
jumlah_mahasiswa = [40, 30, 35, 40, 25, 30, 35]

plt.bar(matkul, jumlah_mahasiswa)
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193510890-92d62162-7665-4c80-8a6a-95f1a94139fe.png" alt="Bar Plot" width="300"/>

## <a name="pie_chart"></a>Pie Chart

*Pie chart* adalah grafik yang menampilkan data dalam bentuk lingkaran. Berikut contoh membuat *pie chart* dengan Matplotlib.

```python
matkul = ['dasprog', 'strukdat', 'pweb', 'pbo', 'paa', 'sbd', 'mbd']
jumlah_mahasiswa = [40, 30, 35, 40, 25, 30, 35]

plt.pie(jumlah_mahasiswa, labels=matkul)
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193511010-372ce310-40d1-4c77-8be8-b0bef2f0c6b7.png" alt="Pie Chart" width="300"/>

## <a name="stacked_bar"></a>Stacked Bar

*Stacked bar* adalah grafik yang menampilkan data dalam bentuk batang yang saling menumpuk. Berikut contoh membuat *stacked bar* dengan Matplotlib.

```python
kota = ['Jakarta', 'Bandung', 'Surabaya', 'Bali']
jumlah_pria = [40, 30, 35, 40]
jumlah_wanita = [25, 30, 35, 20]

plt.bar(kota, jumlah_pria, color='r')
plt.bar(kota, jumlah_wanita, bottom=jumlah_pria, color='b')
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193511078-ca908b0a-8e49-4dc9-942a-ae2343f57df4.png" alt="Stacked Bar" width="300"/>

## <a name="stacked_area"></a>Stacked Area

*Stacked area* adalah grafik yang menampilkan data dalam bentuk area yang saling menumpuk. Berikut contoh membuat *stacked area* dengan Matplotlib.

```python
kota = ['Jakarta', 'Bandung', 'Surabaya', 'Bali']
jumlah_pria = [40, 30, 35, 40]
jumlah_wanita = [25, 30, 35, 20]

plt.stackplot(kota, jumlah_pria, jumlah_wanita, colors=['r', 'b'])
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193511192-430d9d85-e373-4ce0-9a4a-e1ad72910eca.png" alt="Stacked Area" width="300"/>

## <a name="multiple_line"></a>Multiple Line

*Multiple line* adalah grafik yang menampilkan data dalam bentuk garis yang saling berhubungan. Berikut contoh membuat *multiple line* dengan Matplotlib.

```python
negara = ['Indonesia', 'Malaysia', 'Singapura', 'Thailand']
jumlah_penduduk = [250, 150, 100, 200]

plt.plot(negara, jumlah_penduduk, color='r')
plt.plot(negara, jumlah_penduduk, 'ro')
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193511264-ee3a9af2-433f-4775-9dc5-7200c4e1316c.png" alt="Multiple Line" width="300"/>

## <a name="multiple_bar"></a>Multiple Bar

*Multiple bar* adalah grafik yang menampilkan data dalam bentuk batang yang saling berhubungan. Berikut contoh membuat *multiple bar* dengan Matplotlib.

```python
kota = ['Surabaya', 'Jakarta', 'Bandung', 'Bali', 'Medan']
jumlah_anak = [40, 30, 35, 40, 25]
jumlah_dewasa = [25, 30, 35, 20, 30]

barWidth = 0.25
r1 = np.arange(len(jumlah_anak))
r2 = [x + barWidth for x in r1]

plt.bar(r1, jumlah_anak, width=barWidth, color='r', label='anak')
plt.bar(r2, jumlah_dewasa, width=barWidth, color='b', label='dewasa')

plt.xticks([r + barWidth for r in range(len(jumlah_anak))], kota)
plt.legend()
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193511323-e33d48a4-484f-466e-afcf-71c2587d4d0f.png" alt="Multiple Bar" width="300"/>

# <a name="seaborn"></a>Seaborn

Seaborn adalah *library* Python yang berfungsi untuk membuat visualisasi data yang lebih menarik. Seaborn memiliki fungsi yang lebih lengkap dibandingkan dengan Matplotlib. Seaborn juga memiliki fungsi untuk membuat statistik deskriptif.

## <a name="import_seaborn"></a>Import Seaborn

Install Seaborn terlebih dahulu dengan pip.

```
pip install seaborn
```

*Import* *library* Seaborn.

```python
import seaborn as sns
```

Lalu kita akan menggunakan dataset yang sudah disediakan yaitu:

> <a href="https://raw.githubusercontent.com/owid/covid-19-data/master/public/data/vaccinations/country_data/Indonesia.csv">Data Vaksinasi Indonesia</a>

## <a name="seaborn_scatter"></a>Scatter Plot

*Scatter plot* adalah grafik yang menampilkan data dalam bentuk titik. Berikut contoh membuat *scatter plot* dengan Seaborn.

```python
arr_A = np.array([1, 2, 3, 4, 5])
arr_B = np.array([6, 7, 8, 9, 10])

sns.scatterplot(x=arr_A, y=arr_B)
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193511441-e154a09e-7db8-4874-a035-9f2758cdf77a.png" alt="Scatter Plot" width="300"/>

Jika menggunakan dataset yang sudah disediakan, maka kita bisa menggunakan fungsi `sns.scatterplot()` dengan parameter `x` dan `y` yang diisi dengan nama kolom yang akan ditampilkan.

```python
import seaborn as sns
import matplotlib.pyplot as plt
import numpy as np

url = "https://raw.githubusercontent.com/owid/covid-19-data/master/public/data/vaccinations/country_data/Indonesia.csv"
df = pd.read_csv(url, index_col=0)

sns.scatterplot(x=df['total_vaccinations'], y=df['people_vaccinated'])
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193511522-660114de-df71-49c6-973c-459630e63d28.png" alt="Scatter Plot" width="300"/>

## <a name="seaborn_bar"></a>Bar Plot

Seaborn juga memiliki fungsi untuk membuat *bar plot*. Berikut contoh membuat *bar plot* dengan Seaborn.

```python
arr_A = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

sns.barplot(arr_A)
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193511578-c34bfe88-e961-452d-9814-225ec440a4ee.png" alt="Bar Plot" width="300"/>

Menggunakan dataset yang sudah disediakan, kita bisa menggunakan fungsi `sns.barplot()` dengan parameter `x` dan `y` yang diisi dengan nama kolom yang akan ditampilkan.

```python
sns.barplot(x=df['date'], y=df['total_vaccinations'])
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193511643-3234c9dd-9d63-4ae3-af3b-443c4eae9055.png" alt="Bar Plot" width="300"/>

## <a name="seaborn_line"></a>Line Plot

Seaborn juga memiliki fungsi untuk membuat *line plot*. Berikut contoh membuat *line plot* dengan Seaborn.

```python
arr_A = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

sns.lineplot(arr_A)
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193511695-774d237e-63b9-44cb-8ce9-39a5ad4f8e7c.png" alt="Line Plot" width="300"/>

Menggunakan dataset yang sudah disediakan, kita bisa menggunakan fungsi `sns.lineplot()` dengan parameter `x` dan `y` yang diisi dengan nama kolom yang akan ditampilkan.

```python
sns.lineplot(x=df['date'], y=df['total_vaccinations'])
plt.show()
```

## <a name="seaborn_box"></a>Box Plot

*Box plot* adalah grafik yang menampilkan data dalam bentuk kotak. Berikut contoh membuat *box plot* dengan Seaborn.

```python
arr_A = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

sns.boxplot(arr_A)
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193511809-b6d48bb4-723d-44c1-8352-32207439b5a1.png" alt="Box Plot" width="300"/>

Menampilkan *box plot* dengan menggunakan dataset yang sudah disediakan.

```python
sns.boxplot(x=df['date'], y=df['total_vaccinations'])
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193511872-0d6655ff-eb21-4228-bd68-baec12548761.png" alt="Box Plot" width="300"/>

## <a name="seaborn_dist"></a>Distribution Plot

*Distribution plot* adalah grafik yang menampilkan data dalam bentuk distribusi. Berikut contoh membuat *distribution plot* dengan Seaborn.

```python
arr_A = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

sns.distplot(arr_A)
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193515622-354b6f59-475b-47d5-8979-9e832d3ce0db.png" alt="Distributin Plot" width="300">

Menggunakan dataset yang sudah disediakan, kita bisa menggunakan fungsi `sns.distplot()` dengan parameter `x` dan `y` yang diisi dengan nama kolom yang akan ditampilkan.

```python
sns.distplot(df['total_vaccinations'])
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193515801-b10bda0c-52f6-4348-aecb-30cdcd2648aa.png" alt="Distributin Plot" width="300">

## <a name="seaborn_heatmap"></a>Heatmap

*Heatmap* adalah grafik yang menampilkan data dalam bentuk warna. Berikut contoh membuat *heatmap* dengan Seaborn.

```python
arr_A = np.array([[1, 2, 3, 4, 5], [6, 7, 8, 9, 10]])

sns.heatmap(arr_A)
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193515873-916af2f7-0374-4f4e-9c80-bd2f54d05456.png" alt="Heatmap" width="300">

Menampilkan *heatmap* dengan menggunakan dataset yang sudah disediakan.

```python
sns.heatmap(df.corr(), annot=True)
plt.show()
```

<img src="https://user-images.githubusercontent.com/70510279/193515957-d123eda5-331b-4c65-a617-19e9cdd6b042.png" alt="Heatmap" width="300">

# <a name="referensi"></a>Referensi

- https://hub.idbigdata.com/sigit-prasetyo/panduan-praktis-penggunaan-pandas-bagian-1-39
- https://hub.idbigdata.com/sigit-prasetyo/panduan-praktis-penggunaan-pandas-bagian-2-40
- https://ngodingdata.com/tutorial-dasar-numpy-python/
- https://ngodingdata.com/pengenalan-library-matplotlib/
- https://www.geeksforgeeks.org/how-to-plot-a-pandas-dataframe-with-matplotlib/
- https://matplotlib.org/stable/index.html
- https://www.w3schools.com/python/matplotlib_intro.asp
- https://www.geeksforgeeks.org/seaborn-in-python/
- https://seaborn.pydata.org/
