# Implementasi Enkripsi dengan Metode Caesar atau Shift
## Konsep
Enkripsi merupakan metode mengamankan data dengan mengubahnya ke bentuk tertentu agar tidak bisa diketahui orang lain. Enkripsi biasanya digunakan pada pesan militer agar strategi tidak terbaca oleh musuh. Salah satu tokoh terkenal yang menggunakan teknik ini yaitu Julius Caesar yang kemudian tekniknya deberi nama Enkripsi Caesar.
Metode ini menggeser huruf abjad sebanyak n langkah–n bernilai 1-25–sehingga disebut juga Enkripsi Shift. n langkah tersebut berperan sebagai kunci yang nanti bisa di dekripsi sehingga bisa dipahami lagi. Misalnya sebuah teks "Hello World" dienkripsi menggunakan teknik ini dengan **KUNCI = 1**. Itu artinya setiap satu huruf abjad digeser ke kanan sebanyak satu langkah. Maka dari "Hello World" menjadi "Ifmmp Xpsmc". Kemudian untuk mendekripsi pesan tersebut bisa dengan memundurkannya 1 langkah–sesuai kuncinya.

### Contoh lain enkripsi Shift
1. HELLO WORLD -> KHOOR ZRUOG, Kunci = 3 
2. SYAHRIAL HIPDI -> TZBISJBM IJQEJ, 1
3. ABCDE -> FGHIJ, 5

#### Contoh Dekripsi
1. KHOOR ZRUOG -> HELLO WORLD, Kunci = 3
2. NSITSJXNF -> INDONESIA = 5
3. XJUFPGTQF -> SEPAKBOLA = 5
Metode ini mudah untuk dipecahkan dengan cara bruce force karena hanya ada kemungkinan 25 kunci, sesuai dengan jumlah abjad(26, A-Z).

## Implementasi
Untuk menerapkannya metode enkripsi tersebut ke dalam pemograman, ada beberapa batasan dan hal yang perlu diketahui.
**Batasan Masalah**
1. Hanya menenkripsi dan mendekripsi huruf abjad(a-z), karakter lain seperti angka, emot, simbol tidak dienkripsi.
2. Mengubah string menjadi huruf besar atau huruf kecil semua agar konsisten
3. Bahasa yang digunakan adalah Pyhton

**Hal yang perlu diketahui**
1. Kode ASCII
    Dalam dunia nyata, kita bisa memahami teks yang dienkripsi secara konteks. Kita hanya akan mencoba geser satu-per-satu huruf hingga menjadi pesan asli. Namun, komputer tidak bekerja seperti itu. Komputer menggunakan bahasa biner untuk memahami instruksi. Dalam kasus ini, komputer menggunakan
   ASCII merupakan kode yang digunakan komputer untuk membaca karakter. Setiap karakter yang kita lihat seperti alfabet, angka, simbol, hingga tanda baca akan diubah kedalam kode ASCII pada program komputer. Oleh karena itu, kita perlu memahami kode ASCII dan mengubah karakter ke dalam kode ASCII agar dapat dipahami komputer. Di bawah ini merupakan tabel ASCII.
<img width="800" height="600" alt="ASCII-Table" src="https://github.com/user-attachments/assets/b90889e8-f4dd-4462-a8b1-b922b5514df3" />_
_sumber : https://media.geeksforgeeks.org/wp-content/uploads/20240304094301/ASCII-Table.png_
Perhatikan kolom Decimal–informasi yang dibaca oleh komputer dan kolom Char–informasi yang dibaca oleh kita. Pada Decimal 65, Charnya adalah A; pada Decimal 90 Charnya adalah Z; dan pada Decimal 61 charnya adalah =.
Itu artinya adalah huruf A akan disimpan sebagai nilai 65, Z 90, dan sebagainya. Inilah hal yang perlu diperhatikan, kita harus mapping setiap huruf menjadi nilai Decimal. Untuk mempermudah proses, kita perlu menyamakan jenis huruf menjadi kapital semua (65-90) atau menjadi huruf kecil semua (97-122).
Pada kasus ini dipilih jenis huruf kapital sehingga setiap huruf kecil akan diubah menjadi huruf besar: a-> A, b->B, dan seterusnya.
2. Looping
    Fitur dalam bahasa pemograman yang memungkinkan kita dapat memerintah komputer untuk menjalankan tugas sebanyak n kali dengan satu block code. Misalnya, alih-alih kita menulis
   print("HELLO")
   print("HELLO")
   print("HELLO")
   print("HELLO")
   print("HELLO")
   kita dapat menulisnya seperti ini
   for i in range(0,5):
     print("HELLO")
3. modifikasi data
   Modifikasi data adalah proses mengubah nilai dari suatu variable, baik itu bertipe itu integer, string, array, dan lain sebagainya. contoh:
   string teks = "SYAHRIAL HIPDI"
   teks[2] = 'Z'
   Itu artinya kita mengubah index kedua dari teks "A" menjadi Z, sehingga hasil akhirnya menjadi "SYZHRIAL HIPDI". Namun, dalam Pyhton string merupakan tipe data yang tidak bisa diubah(immutable). Jika kita melakukannya, akan muncul error. Oleh karena itu, hal yang akan kita lakukan adalah membuat variable baru untuk hasil enkripsi dan dekripsi 
4. function
   Function merupakan fitur dalam pemograman yang memungkinkan pengguna menulis satu kali block program tapi bisa dijalankan berkali-kali dengan cara memanggilnya. 
5. Modolus
   Modulus atau sisa bagi adalah konsep dalam matematika dimana kita mengambil sisa dari pembagian dua buah bilangan. Contoh:
   5%4 -> 5/4 = 1 sisa 1(5-4*1)
   6%4 -> 6/4 = 1 sisa 2(6-4*1)
   9%4 -> 9/4 = 2 sisa 1(9-4*2)
   11%4 -> 11/4 = 2 sisa 3(9-4*2)
   3%4 -> 3/4 = 0 sisa 3(3-4*0)
   2%4 -> 2/4 = 0 sisa 2(2-4*0)
   4%4 -> 4/4 = 1 sisa 0(4-4*1)
   12%4 -> 12/4 = 3 sisa 0(12-4*3)
6. type casting
   Type casting fitur untuk mengubah tipe data, contohnya pada kode ASCII tadi. Dalam Pyhton kita dapat menggunakan function **ord(argument)** untuk mengubah tipe data dari karakter menjadi desimal.
   Contoh:
   ord('A'), ini artinya kita mengubah char "A" menjadi nilai desimal 65, seperti pada kode ASCII tadi.

## Penjelasan Program
Untuk source code kalian dapat melihatnya di file main.ipynb
