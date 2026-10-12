HAPPY BIRTHDAY DINAMIS

Upload seluruh isi folder ini ke public_html/happybirthdayto/

Tambahkan ke .htaccess pada root domain, SEBELUM routing utama SLiMS:
RewriteEngine On
RewriteRule ^happybirthdayto=([^/]+)/?$ happybirthdayto/index.html?name=$1 [B,L,QSA,NC]

Contoh:
https://digilib.bibliothee.web.id/happybirthdayto=Julaika
https://digilib.bibliothee.web.id/happybirthdayto=Nur%20Aisyah

Alternatif tanpa konfigurasi .htaccess:
https://digilib.bibliothee.web.id/happybirthdayto/?name=Julaika

Jumlah balon mengikuti huruf nama; spasi tidak menjadi balon.
