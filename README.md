# Implementasi Enkripsi dengan Metode Caesar atau Shift
## Konsep
Enkripsi merupakan metode mengamankan data dengan mengubahnya ke bentuk tertentu agar tidak bisa diketahui orang lain. Enkripsi biasanya digunakan pada pesan militer agar strategi tidak terbaca oleh musuh. Salah satu tokoh terkenal yang menggunakan teknik ini yaitu Julius Caesar yang kemudian tekniknya deberi nama Enkripsi Caesar. Metode ini menggeser huruf abjad sebanyak n langkah, sehingga disebut juga Enkripsi Shift.
Contoh : Hello World -> Khoor Zruog.
Contoh diatas adalah enkripsi dengan metode shift dengan kunci 3 langkah. Sehingga A -> D, B->E, Z->C, Y->B.
Kunci yang dibuat tidak harus tiga langkah tapi bisa dari rentang 1-25. Pengirim pesan akan mengirim teks yang sudah dienkripsi beserta kuncinya, sehingga penerima dapat mendekripsi teks dengan memundurkan langkahnya.
Pengirim : ABCD, kunci 3
enkripsi : DEFG
Penerima : ABCD, setelah didekripsi.

## Implementasi
Pada kesempatan kali ini, kita akan mengimplementasi metode enkripsi tersebut ke dalam sebuah pemograman. Adapun hal yang perlu diketahui untuk menerapkan hal itu adalah:
1. Kode ASCII
2. Looping
3. modifikasi array, string, atau tipe data lain
4. function

Di dunia nyata kita dapat langsung melakukan enkripsi atau dekripsi, tapi pada pemograman ada beberapa langkah tambahan sebelum mengeser huruf-huruf abjad. Salah satunya mengonversi teks ke code ASCII. komputer menggunakan code ASCII untuk menampilkan karakter. Misalnya kode ASCII untuk A yaitu 65, B 66, dan Z 90. Setelah dikonversi barulah dilakukan operasi matematik untuk mengubah karakternya. Namun ada permasalah, jika di dunia nyata batasannya adalah 1-26, pada kode ASCII batasannya adalah 0-127. Sehingga kita perlu mengatur batasan agar hasil selalu pada range 65-90. Jika tidak maka akan menghasilkan karakter lain. Contoh jika Z digeser 10 maka hasilnya adalah d, padahal seharusnya J. Selain itu ASCII huruf kapital dan huruf kecil juga beda. ASCII A adalah 65, sedangkan a adalah 97. Kita perlu melakukan preprosessing data terlebih dahulu. Entah semua huruf diubah menjadi kapital, atau menjadi huruf kecil.
