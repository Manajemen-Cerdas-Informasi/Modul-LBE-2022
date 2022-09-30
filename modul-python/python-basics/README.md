# LBE MCI 2022 - Basic Python 

- [LBE MCI 2022 - Basic Python](#lbe-mci-2022---basic-python)
- [<a name="pendahuluan"></a>Pendahuluan](#pendahuluan)
  - [<a name="apa_itu_python"></a>Apa Itu Python?](#apa-itu-python)
    - [Python](#python)
    - [Kenapa Perlu Belajar Python?](#kenapa-perlu-belajar-python)
  - [<a name="install"></a>Install](#install)
    - [Download Python](#download-python)
    - [Install Python](#install-python)
    - [Check Version Python](#check-version-python)
- [<a name="dasar"></a>Dasar](#dasar)
  - [<a name="aritmatika"></a>Aritmatika](#aritmatika)
  - [<a name="print"></a>Print](#print)
  - [<a name="komentar"></a>Komentar](#komentar)
  - [<a name="konstanta_literal"></a>Konstanta Literal](#konstanta-literal)
  - [<a name="string"></a>String](#string)
  - [<a name="format_string"></a>Format String](#format-string)
  - [<a name="variabel"></a>Variabel](#variabel)
  - [<a name="tipe_data"></a>Tipe Data](#tipe-data)
  - [<a name="indentasi"></a>Indentasi](#indentasi)
- [<a name="referensi"></a>Referensi](#referensi)

</br>

# <a name="pendahuluan"></a>Pendahuluan

## <a name="apa_itu_python"></a>Apa Itu Python?

### Python

Python merupakan bahasa pemrograman tingkat tinggi yang diracik oleh **Guido van Rossum**. Python banyak digunakan untuk membuat berbagai macam program, seperti: program CLI, Program GUI (desktop), Aplikasi Mobile, Web, IoT, Game, Program untuk Hacking, dsb. Python juga dikenal dengan bahasa pemrograman yang mudah dipelajari, karena struktur sintaknya rapi dan mudah dipahami. 
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
Langkah pertama adalah mendownload python di web resminya <a href="https://www.python.org/downloads/">Download Python</a>. Sesuaikan dengan OS yang kalian punya. Pilih file yang Installer saja biar memudahkan proses instalasi di device masing-masing.

### Install Python
Install python selayaknya install software pada desktop. </br>
<img src="https://user-images.githubusercontent.com/70510279/192933025-7e3e67f8-37d9-453a-ac1f-f81e0fd15d78.png" alt="Install Python" width="500"/>

### Check Version Python
Setelah diinstall, maka dilakukan cek terlebih dulu supaya bisa mengetahui apakah sudah terinstall atau belum. Selain itu, juga supaya dapat mengetahui versi Python yang terinstall.
```
python --version
```

<img src="https://user-images.githubusercontent.com/70510279/192933850-c262f2af-c303-4fde-b48b-4f569ac8c85b.png" alt="Install Python" width="200"/>

# <a name="dasar"></a>Dasar

## <a name="aritmatika"></a>Aritmatika

Berikut beberapa fungsi aritmatika yang bisa digunakan dalam python yaitu: 
| Simbol    | Deskripsi                 |
| ---       | ---                       |
| +         | Menambahkan dua obyek     |
| -         | Mengurangi dua obyek      |
| *         | Perkalian                 |
| **        | Pangkat                   |
| /         | Pembagian                 |
| //        | Pembagian Bulat ke Bawah  |
| %         | Sisa hasil bagi (modulus) |

## <a name="print"></a>Print
Untuk melakukan print dalam program python maka menggunakan syntax yaitu 
```
print("Kata yang akan di print")
```
> Catatan : Untuk catatan, sebaiknya mengatur teks editor agar indentasi menggunakan spasi sebanyak 4 buah spasi (tab)

## <a name="komentar"></a>Komentar
Komentar adalah teks apapun yang diawali dengan tanda `#`, digunakan untuk memberikan catatan kepada pembaca kode.  Komentar tidak akan terlihat dalam program ketika dijalankan. 
Contoh : 
```
# Ini komentar 
# Ini tidak akan terbaca dalam program
```
## <a name="konstanta_literal"></a>Konstanta Literal
Salah satu contoh konstanta literal yaitu bilangan seperti `5`, `1.23`, atau string seperti `'hari senin'` atau `"hari jum'at"`. Hal ini disebut literal atau harfiah karena bisa menggunakan nilai ini secara langsung.

## <a name="string"></a>String
- Single Quote </br>
    Contoh : </br>
    `'Teknik Informatika'`, </br> `'Hari Jum\'at'`
- Double Quote </br>
    Contoh : </br>
    `"Teknik Informatika"`, </br> `"Hari Jum'at"`
- Triple Quote </br>
    Contoh : </br>
    ```"""Ini adalah contoh multi-line string saya tambahkan single quote (') dan double quote (") """ ```

## <a name="format_string"></a>Format String
> Operator % jika digunakan untuk string bukan berarti modulus melainkan string format.
```
print '%s pergi ke %s' % ('ibu', 'pasar')
print '{0} pergi ke {1}'.format('ibu', 'pasar')

print 'jumlah total: %10.3f' % 10.3333
print 'jumlah total: {0:10.3f}'.format(10.3333)
```

## <a name="variabel"></a>Variabel
Berikut aturan penamaan variabel dalam python:
- Karakter pertama harus berupa karakter alfabet (huruf besar atau huruf kecil ASCII, atau unicode) atau underscore.
- Karakter selanjutnya dapat berupa alfabet (huruf besar atau huruf kecil ASCII, atau unicode), underscore _ atau digit (0-9).
- Nama variabel bersifat case-sensitif. Sebagai contoh, `namaMhs` dan `namamhs` adalah variabel yang berbeda.
```
a = 10
b = 20
c = 30

total = a + b + c
```

## <a name="tipe_data"></a>Tipe Data
Variabel dapat menyimpan nilai dengan berbagi tipe disebut dengan tipe data. Bilangan dan string adalah tipe dasar, yang sudah dibahas sebelumnya.
```
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
Karakter spasi penting untuk bahasa pemrogramman Python. Lebih tepatnya spasi diawal baris atau indentasi. Spasi diawal (baik berupa spasi atau tab) baris logis digunakan untuk menentukan level indentasi, yang akan mempengaruhi pengelompokan statemen.



# <a name="referensi"></a>Referensi
- https://sakti.github.io/python101/index.html
- https://docs.python.org/3/
- https://www.petanikode.com/tutorial/python/