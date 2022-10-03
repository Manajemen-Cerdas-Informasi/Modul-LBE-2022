# LBE MCI 2022 - Basic Python

- [Pendahuluan](#pendahuluan)
  - [Apa Itu Python?](#apa-itu-python)
    - [Python](#python)
    - [Kenapa Perlu Belajar Python?](#kenapa-perlu-belajar-python)
  - [Install](#install)
    - [Download Python](#download-python)
    - [Install Python](#install-python)
    - [Check Version Python](#check-version-python)
- [Dasar](#dasar)
  - [Aritmatika](#aritmatika)
  - [Print](#print)
  - [Input](#input)
  - [Komentar](#komentar)
  - [Konstanta Literal](#konstanta-literal)
  - [String](#string)
  - [Format String](#format-string)
  - [Variabel](#variabel)
  - [Tipe Data](#tipe-data)
  - [Indentasi](#indentasi)
- [Operator & Statement Conditional](#operator_statement)
  - [Operator](#operator)
    - [Urutan](#urutan)
  - [Statement Conditional](#statement_conditional)
    - [If Else](#if_else)
    - [While](#while)
    - [For Loop](#for_loop)
- [Fungsi](#fungsi)
  - [Parameter Fungsi](#parameter_fungsi)
  - [Variabel Lokal](#variabel-lokal)
  - [Statemen Global](#statemen_global)
  - [Argumen Default](#argumen_default)
- [Struktur Data](#struktur_data)
  - [List](#list)
    - [Read List](#read_list)
    - [Insert List](#insert_list)
    - [Update List](#update_list)
    - [Delete List](#delete_list)
  - [Tuple](#tuple)
  - [Dictionary](#dictionary)
    - [read_dictionary](#read_dictionary)
    - [update_dictionary](#update_dictionary)
    - [delete_dictionary](#delete_dictionary)
- [Referensi](#referensi)

</br>

# <a name="pendahuluan"></a>Pendahuluan

## <a name="apa_itu_python"></a>Apa Itu Python?

### Python

Python merupakan bahasa pemrograman tingkat tinggi yang diracik oleh **Guido van Rossum**. Python banyak digunakan untuk membuat berbagai macam program, seperti: Program CLI, Program GUI (desktop), Aplikasi Mobile, Web, IoT, Game, Program untuk Hacking, dsb. Python juga dikenal dengan bahasa pemrograman yang mudah dipelajari karena struktur sintaknya rapi dan mudah dipahami.

> Python bagus untuk pemula yang belum pernah coding

### Kenapa Perlu Belajar Python?

<img src="https://user-images.githubusercontent.com/70510279/192930136-6df334c3-e059-4a2e-9616-c32e63ea32e6.png" alt="Meme Python" width="500"/>

Jadi kenapa belajar Python?

1. Cepat dan efektif
2. Mudah dipelajari
3. Banyak digunakan di perusahaan besar
4. Ingin coba hal baru
5. Masih banyak lagi

## <a name="install"></a>Install

### Download Python

Langkah pertama adalah men-*download* Python di *web* resminya <a href="https://www.python.org/downloads/">di sini</a>. Sesuaikan dengan OS yang kalian punya. Pilih *file* yang *installer* saja biar memudahkan proses instalasi di *device* masing-masing.

### Install Python

*Install* Python selayaknya *install software* pada *desktop*. </br>
<img src="https://user-images.githubusercontent.com/70510279/192933025-7e3e67f8-37d9-453a-ac1f-f81e0fd15d78.png" alt="Install Python" width="500"/>

### Check Version Python

Setelah di-*install*, maka dilakukan cek terlebih dulu supaya bisa mengetahui apakah sudah ter-*install* atau belum. Selain itu, juga supaya dapat mengetahui versi Python yang ter-*install*.

```
python --version
```

<img src="https://user-images.githubusercontent.com/70510279/192933850-c262f2af-c303-4fde-b48b-4f569ac8c85b.png" alt="Install Python" width="200"/>

# <a name="dasar"></a>Dasar

## <a name="aritmatika"></a>Aritmatika

Berikut beberapa fungsi aritmatika yang bisa digunakan dalam Python yaitu:
| Simbol | Deskripsi |
| --- | --- |
| + | Menambahkan dua obyek |
| - | Mengurangi dua obyek |
| \* | Perkalian |
| \*\* | Pangkat |
| / | Pembagian |
| // | Pembagian Bulat ke Bawah |
| % | Sisa hasil bagi (modulus) |

## <a name="print"></a>Print

Untuk melakukan *print* dalam program Python maka menggunakan sintaks yaitu

```python
print("Kata yang akan di print")
```

> Catatan : Untuk catatan, sebaiknya mengatur teks editor agar indentasi menggunakan spasi sebanyak 4 buah spasi (*tab*)

## <a name="input"></a>Input

Untuk melakukan input dalam program Python maka menggunakan sintaks yaitu

```python
input("Masukkan Inputan:")
```

## <a name="komentar"></a>Komentar

Komentar adalah teks apapun yang diawali dengan tanda `#`, digunakan untuk memberikan catatan kepada pembaca kode. Komentar tidak akan terlihat dalam program ketika dijalankan.
Contoh :

```python
# Ini komentar
# Ini tidak akan terbaca dalam program
```

## <a name="konstanta_literal"></a>Konstanta Literal

Salah satu contoh konstanta literal yaitu bilangan seperti `5`, `1.23`, atau *string* seperti `'hari senin'` atau `"hari jum'at"`. Hal ini disebut literal atau harfiah karena bisa menggunakan nilai ini secara langsung.

## <a name="string"></a>String

- **Single Quote** </br>
  Contoh : </br>
  `'Teknik Informatika'`, </br> `'Hari Jum\'at'`
- **Double Quote** </br>
  Contoh : </br>
  `"Teknik Informatika"`, </br> `"Hari Jum'at"`
- **Triple Quote** </br>
  Contoh : </br>
  `"""Ini adalah contoh multi-line string saya tambahkan single quote (') dan double quote (") """ `

## <a name="format_string"></a>Format String

> Operator % jika digunakan untuk *string* bukan berarti modulus melainkan *string* format.

```python
print("%s pergi ke %s" % ('Kurnia', 'gedung TC'))
print("{0} pergi ke {1}".format('Bapak', 'kantor'))

print("Jumlah total: %10.3f" % 10.3333)
print("Jumlah total: {0:10.3f}".format(10.3333))
```

## <a name="variabel"></a>Variabel

Berikut aturan penamaan variabel dalam Python:

- Karakter pertama harus berupa karakter alfabet (huruf besar atau huruf kecil ASCII, atau unicode) atau *underscore*.
- Karakter selanjutnya dapat berupa alfabet (huruf besar atau huruf kecil ASCII, atau unicode), *underscore* \_ atau digit (0-9).
- Nama variabel bersifat *case*-*sensitive*. Sebagai contoh, `namaMhs` dan `namamhs` adalah variabel yang berbeda.

```python
a = 10
b = 20
c = 30

total = a + b + c
```

## <a name="tipe_data"></a>Tipe Data

Variabel dapat menyimpan nilai dengan berbagi tipe disebut dengan tipe data. Bilangan dan *string* adalah tipe dasar, yang sudah dibahas sebelumnya.

```python
type(1)
<type 'int'>

type(3.2)
<type 'float'>

type(2 ** 1000)
<type 'long'>

type('abc')
<type 'str'>

type('a')
<type 'str'>
```

## <a name="indentasi"></a>Indentasi

Karakter spasi penting untuk bahasa pemrograman Python. Lebih tepatnya spasi di awal baris atau indentasi. Spasi di awal (baik berupa spasi atau *tab*) baris logis digunakan untuk menentukan level indentasi, yang akan mempengaruhi pengelompokan *statement*.

# <a name="operator_statement"></a>Operator & Statement Conditional

## <a name="operator"></a>Operator

<img src="https://user-images.githubusercontent.com/70510279/193294569-18c7dd58-b06a-44c3-b2ba-2b43a6453e86.png" alt="Install Python" width="1000"/>

### <a name="urutan"></a>Urutan

Urutan sama seperti pengerjaan matematika pada umumnya. Misalnya perkalian lebih tinggi dari penjumlahan.

## <a name="statement_conditional"></a>Statement Conditional

### <a name="if_else"></a>If Else

Digunakan untuk mengecek kondisi. Jika kondisi `if` bernilai benar, maka kita akan menjalankan *statement*, jika tidak akan diteruskan dengan *statement* `else`.

```python
if hewan == "ayam":
  print "Keluarga Unggas"
elif hewan == "kambing":
  print "Keluarga Mamalia"
else:
  print "Keluarga Serangga"
```

### <a name="while"></a>While

`While` merupakan *statement* untuk perulangan dan akan dijalankan terus menerus selama kondisi benar.

```python
n = 10

sum = 0
i = 1

while i <= n:
  sum = sum + i
  i = i+1

print(sum)
```

### <a name="for_loop"></a>For Loop

`For Loop` merupakan *statement* untuk perulangan yang memiliki batasan dalam melakukan perulangannya sesuai yang telah ditentukan.

```python
genre = ['dangdut', 'pop', 'indie', 'rock']

for i in range(len(genre)):
  print("Saya suka musik", genre[i])
```

# <a name="fungsi"></a>Fungsi

Fungsi adalah bagian dari program yang dapat digunakan ulang.
Fungsi dalam Python didefinisikan menggunakan kata kunci `def`. Setelah `def` ada nama pengenal fungsi diikut dengan parameter yang diapit oleh tanda kurung dan diakhir dingan tanda titik dua `:`

```python
def pemain_bola_terbaik():
    print("Lionel Messi")

pemain_bola_terbaik()  # => "Lionel Messi"
```

## <a name="parameter_fungsi"></a>Parameter Fungsi

Fungsi dapat membaca parameter, parameter adalah nilai yang disediakan kepada fungsi, dimana nilai ini akan menentukan `output` yang akan dihasilkan fungsi.

```python
def cetak_maksimal(a, b):
    if a > b:
        print("%s merupakan nilai maksimal" % a)
    elif a == b:
        print("%s sama dengan %s" % (a, b))
    else:
        print("%s merupakan nilai maksimal" % b)

cetak_maksimal(10, 5)
```

## <a name="variabel_lokal"></a>Variabel Lokal

Jika ada variabel yang dideklarasikan di dalam fungsi, variabel ini tidak ada kaitannya dengan variabel lain dengan nama yang sama di luar fungsi sehingga hanya bisa berjalan di dalam fungsi tersebut.

```python
x = 50

def fungsi(x):
  print("x = ", x)
  x = 2
  print("merubah lokal variabel x = ", x)

fungsi(100)

print("nilai x masih %s" % x)
```

## <a name="statemen_global"></a>Statement Global

Statement Global digunakan supaya variabel bisa diakses di luar fungsi.

```python
x = 50

def fungsi():
    print("x = ", x)

def fungsi2():
    x = 100  # menulis ke lokal variabel
    print("x = ", x)

def fungsi3():
    global x
    x = 100
    print("x = ", x)

fungsi()
print("nilai x fungsi-1 = ", x, "\n")

fungsi2()
print("nilai x fungsi-2 = ", x, "\n")

fungsi3()
print("nilai x fungsi-3 = ", x, "\n")
```

## <a name="argumen_default"></a>Argumen Default

Untuk beberapa fungsi yang ingin menyediakan paramater opsional dan menggunakan nilai *default* jika tidak menyediakan argumen saat fungsi dipanggil, maka bisa menggunakan `=` pada paramaternya.

```python
def mcd(pesan, jumlah=1):
    print(pesan, jumlah)

mcd('Ayam Goreng')
mcd('Ayam Goreng', 3)
```

# <a name="struktur_data"></a>Struktur Data

Struktur Data adalah struktur yang dapat menyimpan dan mengorganisasikan kumpulan data.

## <a name="list"></a>List

*List* adalah struktur data yang menyimpan koleksi data terurut yang dapat menyimpan *sequence*/rangkaian item menggunakan *list*.
</br>
Item dalam *list* ditutup menggunakan kurung siku `[]` (*list literal*). Setelah *list* dibuat kita bisa menambah, mengurangi, dan mencari item pada *list* sehingga *list* bersifat `mutable`.

### <a name="read_list"></a>Read List

Untuk mengakses nilai *list* dalam Python, maka gunakan kurung siku untuk membagi antar *index* yang tersedia.

```python
list1 = ['Pengabdi Setan', 'Mencuri Raden Saleh', 'KKN Desa Penari']
list2 = [100, 200, 300], [400, 500, 600], [700, 800, 900]

print("list1[0]: ", list1[0])
print("list2[2]: ", list2[2])
```

### <a name="insert_list"></a>Insert List

Untuk memasukkan nilai dari suatu *list*, maka bisa menggunakan fungsi `append()`.

```python
list = ['Pengabdi Setan', 'Mencuri Raden Saleh', 'KKN Desa Penari']
list.append('Keluarga Cemara')

print(list)
```

### <a name="update_list"></a>Update List

Untuk memperbarui nilai dari suatu *list*, maka bisa langsung memasukkan nilai menggunakan `=`.

```python
list = ['Pengabdi Setan', 'Mencuri Raden Saleh', 'KKN Desa Penari']
print("Sebelum Diganti: ", list[2])

list[2] = 'Miracle In Cell No. 7'
print("Sebelum Diganti: ", list[2])
```

### <a name="delete_list"></a>Delete List

Untuk menghapus nilai dari suatu *list*, maka bisa menggunakan fungsi `remove()`.

```python
list = ['Pengabdi Setan', 'Mencuri Raden Saleh',
        'KKN Desa Penari', 'Miracle In Cell No. 7']
list.remove('KKN Desa Penari')

print(list)
```

## <a name="tuple"></a>Tuple

*Tuple* mirip dengan *list*, namun *tuple* bersifat *immutable* (tidak bisa diubah setelah didefinisikan). Item dalam *tuple* menggunakan diapit dalam tanda `()`.

```python
tup1 = ('Nayeon', 'Jihyo', 'Momo', 'Sana',
        'Mina', 'Dahyun', 'Chaeyoung', 'Tzuyu')
tup2 = (1, 2, 3, 4, 5, 6, 7)

print("tup1[0]: ", tup1[0])
print("tup2[1:5]: ", tup2[1:5])
```

## <a name="dictionary"></a>Dictionary

*Dictionary* seperti buku alamat, dengan buku alamat kita bisa mencari alamat atau detail kontak hanya menggunakan nama orang yang kita cari. Kita mengasosiasikan `key` (nama) dengan `value` (detail).

### <a name="read_dictionary"></a>Read Dictionary

Untuk mengakses elemen *dictionary*, kita dapat menggunakan tanda kurung siku bersama dengan *key* untuk mendapatkan nilainya.

```python
dict = {'Name': 'Kurnia', 'Age': 20, 'Laboratory': 'IIM'}

print("dict['Name']: ", dict['Name'])
print("dict['Laboratory']: ", dict['Laboratory'])
```

### <a name="update_dictionary"></a>Update Dictionary

Untuk memperbarui *dictionary* dengan menambahkan entri baru atau pasangan nilai kunci, memodifikasi entri yang ada, atau menghapus entri.

```python
dict = {'Name': 'Kurnia', 'Age': 20, 'Laboratory': 'IIM'}
dict['Name'] = 'Kurnia Cahya'
dict['Address'] = 'Surabaya'

print("dict['Name']: ", dict['Name'])
print("dict['Address']: ", dict['Address'])
```

### <a name="delete_dictionary"></a>Delete Dictionary

Untuk menghapus *dictionary* dapat dilakukan dengan banyak cara disesuaikan dengan bagian apa yang ingin dihapus.

```python
dict = {'Name': 'Kurnia', 'Age': 20, 'Laboratory': 'IIM'}

del dict['Age']  # Remove entry with key 'Age'
print(dict)

dict.clear()  # Remove all entries in dict
print(dict)
```

# <a name="referensi"></a>Referensi

- https://sakti.github.io/python101/index.html
- https://docs.python.org/3/
- https://www.petanikode.com/tutorial/python/
