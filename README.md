# Payload blokir situs dan file pada mikrotik layer 7 protocol

## Payload Blokir Situs Di Layer 7 Protocol Mikrotik
`^.+(urlsitus).*$`

## Keterangan

`^` Menandakan awal dari string.

`.+` Mencocokkan satu atau lebih karakter apapun kecuali karakter baris baru.

`(urlsitus)` Merupakan penggunaan tanda kurung untuk membuat grup pengecoh dalam regex. Namun, dalam kasus ini, "urlsitus" digunakan sebagai teks biasa, bukan sebagai pola yang spesifik.

`.*` Mencocokkan nol atau lebih karakter apapun kecuali karakter baris baru.

`$` - Menandakan akhir dari string.



## Payload Blokir File Di Layer 7 Protocol Mikrotik
`GET .*(\.pdf)[^a-zA-Z0-9].*HTTP.*\n`

## Keterangan

`GET` Merupakan bagian dari protokol HTTP yang menandakan permintaan untuk mengambil (mengunduh) suatu halaman atau file dari server.

`.*(\.pdf)`  Mengidentifikasi ekstensi file yang diakhiri dengan ".pdf". Tanda "" sebelum titik (.) merupakan escape character yang digunakan untuk mencocokkan karakter titik secara harfiah, bukan sebagai karakter khusus dalam regex.

`[^a-zA-Z0-9]` Mengidentifikasi karakter setelah ekstensi file ".pdf" yang tidak boleh berupa huruf (baik huruf besar maupun huruf kecil) atau angka. Tanda "^" di awal tanda kurung siku ([]) berarti "tidak", sehingga `[^a-zA-Z0-9]` berarti mencocokkan karakter yang bukan huruf atau angka.

`.*HTTP.*` Mengidentifikasi adanya teks "HTTP" di dalam permintaan.

`\n` Mengidentifikasi karakter baris baru (newline) setelah permintaan HTTP.
