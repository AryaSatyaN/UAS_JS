Galeri Seni Digital

Project UAS – Vanilla JavaScript
Aplikasi web Galeri Seni Digital yang menampilkan koleksi karya seni menggunakan Public API.
Project ini dibuat tanpa framework (pure Vanilla JavaScript) dan berfokus pada pengambilan data API, manipulasi DOM, serta interaksi user.

📌 Deskripsi Singkat
Galeri Seni Digital menampilkan daftar karya seni secara dinamis dari API Art Institute of Chicago.
Pengguna dapat melakukan pencarian, filter artis, sorting data, melihat detail karya, serta mengganti tampilan mode terang dan gelap.

🚀 Fitur Utama
📡 Mengambil data dari Public API
🔍 Pencarian judul karya (berdasarkan huruf awal)
🎭 Filter berdasarkan artist
🔠 Sorting judul (Ascending / Descending)
📄 Pagination & Load More
🖼 Modal detail karya seni (gambar resolusi tinggi)
🌙 Dark Mode / Light Mode
📱 Responsive (desktop & mobile)
🧱 Teknologi yang Digunakan
   -HTML5 – struktur halaman
   -CSS3 – styling & dark mode
   -Vanilla JavaScript – logika aplikasi

Public API – Art Institute of Chicago

📂 Struktur Folder
UAS_JS/
├── index.html      # Struktur halaman
├── style.css       # Styling + dark/light mode
├── script.js       # Logika API, search, filter, DOM
└── README.md       # Dokumentasi project

🌐 Sumber API
Project ini menggunakan Art Institute of Chicago Public API:
https://api.artic.edu/api/v1/artworks

Format data: JSON
Tidak membutuhkan API Key
Mendukung pagination
Gambar menggunakan IIIF Image API

⚙️ Cara Menjalankan Aplikasi
Download / clone project
Buka file index.html menggunakan browser
(atau gunakan Live Server di VS Code)
Pastikan koneksi internet aktif
Aplikasi akan memuat data secara otomatis dari API

🔄 Alur Kerja Web
Halaman dimuat (index.html)
JavaScript (script.js) dijalankan
Aplikasi melakukan fetch() ke API
Data JSON diterima dari API
Data diproses (search, filter, sorting)
Data ditampilkan ke halaman menggunakan DOM manipulation
User berinteraksi dengan aplikasi tanpa reload halaman

🎛 Penjelasan Fitur Filter Artist
Dropdown artist dihasilkan secara dinamis dari data yang telah dimuat oleh API.
Karena API menggunakan pagination dan jumlah data sangat besar, artist tidak dimuat sekaligus untuk menjaga performa Web.
Pendekatan ini dipilih agar aplikasi tetap ringan dan efisien.

🌗 Dark Mode
Tombol dark/light mode tersedia di navbar
Preferensi tema disimpan menggunakan localStorage
Tema akan tetap sama saat halaman di-refresh

⚠️ Catatan
Tidak semua data API memiliki nama artist
Jumlah artist yang tampil tergantung data yang sedang dimuat
Pendekatan ini sesuai untuk aplikasi berbasis client-side dan pembelajaran API

🎓 Tujuan Project

Project ini dibuat untuk memenuhi Project UAS dengan tujuan:
   -Memahami penggunaan Public API
   -Menguasai fetch, async/await
   -Melatih DOM manipulation
   -Menerapkan fitur interaktif tanpa framework

👨‍💻 Pengembang
Project dikerjakan sebagai bagian dari tugas UAS
Menggunakan Vanilla JavaScript tanpa library tambahan.

📜 Lisensi
Project ini menggunakan Public API dan ditujukan untuk
pembelajaran dan non-komersial.
