# 🎂 Happy Birthday Dinamis

Halaman ucapan ulang tahun interaktif yang dapat dipersonalisasi hanya dengan mengganti nama pada URL. Proyek ini merupakan pengembangan dari template animasi ulang tahun berbasis HTML, CSS, dan JavaScript, dengan **balon dinamis berbasis CSS** serta teks ucapan yang otomatis menyesuaikan nama penerima.

## 🌐 Demo

**[Lihat demo: Happy Birthday Maryam](https://digilib.bibliothee.web.id/happybirthdayto/?name=Maryam)**

Contoh URL lain:

```text
https://digilib.bibliothee.web.id/happybirthdayto/?name=Julaika
https://digilib.bibliothee.web.id/happybirthdayto/?name=Yustina
https://digilib.bibliothee.web.id/happybirthdayto/?name=Maryam
https://digilib.bibliothee.web.id/happybirthdayto/?name=Nur%20Aisyah
```

## ✨ Fitur

- **Nama dari URL:** parameter `?name=Nama` menentukan nama penerima.
- **Balon otomatis:** satu huruf nama ditampilkan pada setiap balon; jumlah balon menyesuaikan panjang nama.
- **Balon CSS:** bentuk, warna, efek kilau, dan tali dibuat dengan CSS tanpa mengandalkan gambar balon `b1.png`–`b7.png`.
- **Warna bergantian:** palet warna berulang otomatis untuk nama panjang.
- **Ucapan personal:** kalimat `a very happy birthday Nama` mengikuti nama dari URL.
- **Animasi interaktif:** lampu, musik, dekorasi, balon, kue, lilin, dan pesan ulang tahun tetap tersedia dari proyek aslinya.
- **Tanpa database:** satu halaman dapat dipakai untuk banyak nama.

## 🚀 Instalasi

1. Unduh atau *clone* repository ini.
2. Unggah berkas proyek ke direktori server, misalnya `public_html/happybirthdayto/`.
3. Pastikan `index.html`, `stylesheet.css`, `effect.js`, serta aset pendukung (audio, gambar dekorasi, dan sebagainya) berada pada lokasi yang sesuai dengan referensi di HTML/CSS.
4. Buka halaman dengan parameter `name`:

   ```text
   https://domain-anda.com/happybirthdayto/?name=Nova
   ```

> **Catatan:** URL `?name=Nova` tidak memerlukan aturan `.htaccess` khusus. Jika proyek memakai dependensi dari CDN, pastikan koneksi internet tersedia atau sediakan dependensi secara lokal.

## 🔗 URL Alternatif (Opsional)

Jika ingin mendukung URL seperti:

```text
https://domain-anda.com/happybirthdayto=Nova
```

Pada server Apache dengan `mod_rewrite` aktif, tambahkan aturan berikut ke `.htaccess` di root domain:

```apache
RewriteEngine On
RewriteRule ^happybirthdayto=([^/]+)/?$ happybirthdayto/index.html?name=$1 [B,L,QSA,NC]
```

Letakkan aturan sebelum aturan *catch-all* aplikasi lain. Penggunaan URL alternatif ini opsional; format yang direkomendasikan tetap `?name=Nova`.

## 🧩 Cara Kerja

JavaScript membaca parameter `name` dari URL, lalu membuat elemen balon berdasarkan huruf-huruf nama. Elemen ucapan menggunakan target berikut:

```html
<p>a very happy birthday <span id="birthday-name"></span></p>
```

Kemudian nama diisi secara aman melalui `textContent`, bukan `innerHTML`:

```javascript
const params = new URLSearchParams(window.location.search);
const name = (params.get('name') || 'Yustina').trim();
const target = document.getElementById('birthday-name');
if (target) target.textContent = name;
```

> Cuplikan di atas hanya menunjukkan prinsip penggantian teks. Pembuatan balon dan animasi mengikuti implementasi lengkap di berkas proyek.

## 📁 Berkas Utama

| Berkas | Fungsi |
| --- | --- |
| `index.html` | Struktur halaman, teks ucapan, dan pengambilan nama dinamis |
| `stylesheet.css` | Tampilan, tata letak, dan desain balon CSS |
| `effect.js` | Animasi dan interaksi halaman |
| `loading.css` | Tampilan animasi pemuatan |
| `cake.less` | Gaya visual kue ulang tahun |
| `hbd.mp3` | Musik ulang tahun |
| Aset gambar lain | Dekorasi dan elemen visual tambahan |

## 📱 Catatan Penggunaan

- Untuk nama dengan spasi, gunakan URL yang telah di-*encode*, misalnya `Nur%20Aisyah`.
- Nama yang sangat panjang dapat membutuhkan ruang lebih besar pada layar kecil.
- Jika musik tidak langsung berbunyi, klik tombol pemutar; sebagian browser membatasi pemutaran audio otomatis.
- Jangan menghapus aset dekorasi yang masih digunakan oleh HTML atau CSS meskipun balon utama sudah menggunakan CSS.

## 🤝 Kontribusi

Masukan, laporan masalah, dan *pull request* dipersilakan. Saat melaporkan masalah, sertakan URL contoh, perangkat/browser, serta langkah untuk mereproduksinya.

## 📜 Kredit dan Lisensi

Proyek ini merupakan modifikasi dari template halaman ulang tahun yang telah ada. **Pertahankan atribusi dan ketentuan lisensi sumber asli** sesuai berkas atau informasi lisensi yang menyertai proyek asal. README ini tidak menetapkan lisensi baru untuk kode atau aset pihak ketiga.

---

**🎉 Satu halaman, banyak nama, dan ucapan ulang tahun yang lebih personal!**
