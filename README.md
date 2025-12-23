# 🎨 Galeri Seni Digital
**Project UAS – Vanilla JavaScript**

Aplikasi web galeri seni digital yang menampilkan koleksi karya seni
menggunakan **Public API**. Project ini dibuat tanpa framework
(**pure Vanilla JavaScript**) dan berfokus pada pengambilan data API,
manipulasi DOM, serta interaksi user.

---

## 📌 Deskripsi
Galeri Seni Digital menampilkan daftar karya seni secara dinamis dari
Art Institute of Chicago API. Pengguna dapat melakukan pencarian judul,
filter artist, sorting data, melihat detail karya, serta mengganti
tampilan mode terang dan gelap.

---

## 🚀 Fitur Utama
- 📡 Fetch data dari Public API
- 🔍 Pencarian judul karya (huruf awal)
- 🎭 Filter berdasarkan artist
- 🔠 Sorting judul (Ascending / Descending)
- 📄 Pagination & Load More
- 🖼 Modal detail karya seni (gambar HD)
- 🌙 Dark Mode / Light Mode
- 📱 Responsive (desktop & mobile)

---

## 🧱 Teknologi yang Digunakan
- HTML5
- CSS3
- Vanilla JavaScript
- Public API (Art Institute of Chicago)

---

## 📂 Struktur Folder
```text
project-folder/
├── index.html
├── style.css
├── script.js
└── README.md
```

---

##🌐 Sumber API

Art Institute of Chicago Public API
https://api.artic.edu/api/v1/artworks


Format data: JSON
Tidak membutuhkan API Key
Mendukung pagination
Gambar menggunakan IIIF Image API

---

##⚙️ Cara Menjalankan
Buka file index.html di browser
(atau gunakan Live Server di VS Code)
Pastikan koneksi internet aktif
Data akan dimuat otomatis dari API

---

##🔄 Alur Kerja Aplikasi
Halaman dimuat (index.html)
JavaScript dijalankan (script.js)
Aplikasi melakukan fetch() ke API
Data JSON diterima
Data diproses (search, filter, sorting)
Data ditampilkan menggunakan DOM manipulation
User berinteraksi tanpa reload halaman

---

##🎛 Filter Artist
Dropdown artist dibuat secara dinamis dari data yang sedang dimuat.
Karena API menggunakan pagination dan jumlah data sangat besar, artist
tidak dimuat sekaligus agar performa aplikasi tetap ringan dan stabil.

---

##🔢 Catatan Filter Angka
Aplikasi ini tidak menggunakan filter numerik karena data utama yang
ditampilkan bersifat tekstual (judul dan nama artist). Informasi numerik
seperti tahun tidak selalu tersedia dalam format angka yang konsisten
pada API, sehingga filter berbasis teks lebih relevan.

---

##🌗 Dark Mode
Tombol tersedia di navbar
Preferensi tema disimpan menggunakan localStorage
Tema tetap tersimpan saat halaman di-refresh

---

##🎓 Tujuan Project
Project ini dibuat untuk memenuhi Project UAS, dengan tujuan:
Memahami penggunaan Public API
Menggunakan fetch, async/await, dan error handling
Melatih DOM manipulation tanpa framework
Membangun fitur interaktif berbasis client-side

---

##👨‍💻 Pengembang
Project UAS – Vanilla JavaScript
Dibuat untuk keperluan pembelajaran dan akademik.

---

##📜 Lisensi
Menggunakan Public API dan ditujukan untuk penggunaan
non-komersial dan pembelajaran.

---
