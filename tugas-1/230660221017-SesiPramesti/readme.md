Tugas 1 — Identifikasi Kebutuhan Aplikasi Bergerak

SI-FASKAM — Sistem Informasi Pengaduan Fasilitas Kampus

Identitas
Keterangan	Data
Nama	Sesi Pramesti
NIM	230660221017
Program Studi	Sistem Informasi
Domain	Perpustakaan Kampus
Nama Aplikasi	SI Faskam (Sistem Informasi Pengaduan Fasilitas Kampus)
Platform	Mobile
Framework	Flutter

Project

SI-FASKAM

1. Deskripsi Sistem

SI-FASKAM (Sistem Informasi Pengaduan Fasilitas Kampus) merupakan aplikasi mobile yang ditujukan untuk mahasiswa agar dapat melaporkan fasilitas kampus yang mengalami masalah, seperti kursi atau meja rusak, lampu mati, AC bermasalah, toilet rusak, dan fasilitas lainnya. Masalah yang ingin diselesaikan adalah proses pelaporan yang masih dapat dilakukan secara manual sehingga mahasiswa harus menyampaikan keluhan secara langsung dan sulit mengetahui perkembangan laporan yang sudah dibuat. Aplikasi mobile dipilih karena mahasiswa dapat mengirim pengaduan saat berada di lokasi kejadian dengan memanfaatkan konteks bergerak, serta proses pengaduan dapat dibuat singkat melalui interaksi sentuh pada ponsel; selain itu, aplikasi dapat memanfaatkan kamera dan lokasi untuk melengkapi laporan.

Tujuan Sistem

SI-FASKAM dirancang untuk membantu mahasiswa menyampaikan pengaduan fasilitas dengan lebih mudah dan membantu proses pengelolaan laporan secara terstruktur. Pada sisi mahasiswa, aplikasi digunakan untuk membuat laporan, melihat daftar laporan, melihat detail, dan memantau status pengaduan. Pengelolaan dan perubahan status oleh petugas dilakukan melalui backend/admin Sistem Informasi dan tidak menjadi fokus utama aplikasi mobile mahasiswa.

2. Ruang Lingkup Sistem

Aplikasi Mobile (Flutter)

Fitur yang direncanakan pada aplikasi mahasiswa:

Login pengguna

Dashboard

Melihat daftar pengaduan

Melihat detail pengaduan

Membuat pengaduan baru

Memilih kategori pengaduan

Menulis deskripsi masalah

Menambahkan foto fasilitas yang bermasalah

Menambahkan lokasi pengaduan

Melihat status pengaduan

Melihat profil pengguna

Di Luar Lingkup Aplikasi Mobile

Beberapa proses dilakukan pada backend/admin Sistem Informasi, yaitu:

Pengelolaan data seluruh pengguna

Pengelolaan kategori fasilitas

Verifikasi pengaduan oleh petugas

Perubahan status pengaduan oleh petugas

Pengelolaan data dan laporan pada sisi server

Catatan: Kebutuhan yang dikerjakan petugas/admin dicantumkan sebagai di luar lingkup aplikasi mobile (backend SI) agar batas antara aplikasi mobile dan backend tetap jelas.

3. Diagram Arsitektur

Arsitektur SI-FASKAM menggunakan pola client-server sederhana. Aplikasi Flutter mengirim HTTP Request dalam format JSON ke REST API, backend memproses permintaan dan berkomunikasi dengan database, kemudian hasilnya dikirim kembali ke aplikasi melalui HTTP Response.

Diagram



Alur Komunikasi

Aplikasi Mobile (Flutter)
        |
        | HTTP Request (JSON)
        v
Backend SI-FASKAM (REST API)
        |
        | Query / perubahan data
        v
Database SI-FASKAM
        |
        | Data hasil query
        v
Backend SI-FASKAM
        |
        | HTTP Response (JSON)
        v
Aplikasi Mobile (Flutter)

File sumber diagram tersedia pada:

diagram.mmd

diagram.png

4. Tabel Kebutuhan Aplikasi

No.

Permintaan

Pengguna

Karakteristik Mobile yang Terkait

Fitur Aplikasi

Materi Pemenuh

1

Pengguna dapat masuk ke aplikasi menggunakan akun

Mahasiswa

Sesi penggunaan singkat, interaksi sentuh

Halaman login dan validasi form

Minggu 3, 5–6

2

Pengguna dapat melihat daftar pengaduan yang pernah dibuat

Mahasiswa

Layar kecil, sesi penggunaan singkat

Halaman daftar pengaduan

Minggu 3, 5–6

3

Pengguna dapat melihat detail pengaduan

Mahasiswa

Layar kecil, interaksi sentuh

Halaman detail pengaduan

Minggu 3, 5–6

4

Pengguna dapat membuat pengaduan fasilitas baru

Mahasiswa

Interaksi sentuh, konteks bergerak

Form pengaduan

Minggu 5–6

5

Pengguna dapat menambahkan foto kondisi fasilitas

Mahasiswa

Konteks bergerak, pemanfaatan fitur perangkat

Kamera/pilih gambar

Minggu 11

6

Pengguna dapat menambahkan lokasi fasilitas yang bermasalah

Mahasiswa

Konteks bergerak

Lokasi/GPS

Minggu 11

7

Pengguna dapat melihat perubahan status pengaduan

Mahasiswa

Sesi penggunaan singkat, konektivitas

Status pengaduan dan riwayat

Minggu 9–10, 11

8

Petugas memverifikasi laporan dan mengubah status pengaduan

Petugas

—

Di luar lingkup aplikasi mobile (backend SI)

Minggu 9–10

Keterangan Karakteristik Mobile

Interaksi sentuh digunakan karena proses utama dilakukan melalui tombol, menu, dan form pada layar ponsel.

Sesi penggunaan singkat penting karena mahasiswa sebaiknya dapat membuat atau mengecek pengaduan dalam beberapa langkah.

Konteks bergerak relevan karena pengaduan dapat dibuat langsung ketika mahasiswa menemukan fasilitas yang bermasalah di lokasi tertentu.

Konektivitas terbatas perlu dipertimbangkan agar aplikasi dapat menangani kondisi jaringan yang lambat atau terputus dengan menampilkan pesan yang jelas dan, pada pengembangan berikutnya, dapat menggunakan penyimpanan lokal untuk data sementara.

5. User Flow Utama

Alur utama yang direncanakan untuk mahasiswa adalah:

Login
  ↓
Dashboard
  ↓
Buat Pengaduan
  ↓
Pilih Kategori
  ↓
Isi Deskripsi
  ↓
Tambah Foto
  ↓
Tambah Lokasi
  ↓
Kirim Pengaduan
  ↓
Pengaduan Berhasil
  ↓
Lihat Status Pengaduan

Alur untuk mengecek laporan:

Login
  ↓
Dashboard
  ↓
Daftar Pengaduan
  ↓
Pilih Pengaduan
  ↓
Detail Pengaduan
  ↓
Lihat Status

6. Rencana Pengembangan Sampai UAS

Pengembangan SI-FASKAM dilakukan secara bertahap mengikuti materi Pemrograman Aplikasi Bergerak.

Minggu

Fokus

Target SI-FASKAM

1

Konsep aplikasi bergerak dan environment

Menentukan domain, membuat Tugas 1, menyiapkan Flutter

2

Dasar Dart

Memahami variabel, fungsi, kondisi, perulangan, dan collection

3

Struktur Flutter dan widget

Membuat struktur project, MaterialApp, Scaffold, dan widget dasar

4

Analisis kebutuhan

Menentukan aktor, kebutuhan, use case, dan user flow

5

UI/UX

Membuat wireframe dan rancangan tampilan SI-FASKAM

6

Implementasi UI dan navigasi

Membuat login, dashboard, daftar, detail, dan form pengaduan

7

Data lokal

Menyimpan data/session atau draft pengaduan secara lokal

8

UTS

Menunjukkan prototype SI-FASKAM dan hasil perkembangan project

9

REST API

Menyiapkan endpoint backend SI-FASKAM

10

Integrasi SI

Menghubungkan Flutter dengan REST API dan database

11

Fitur perangkat

Menambahkan kamera, lokasi, dan notifikasi sesuai kebutuhan

12

Validasi dan keamanan

Permission, autentikasi, token, dan penyimpanan yang lebih aman

13

Testing dan debugging

Menguji fitur utama dan memperbaiki error

14

Penyempurnaan

Memperbaiki UI, validasi, alur, dan integrasi

15

Dokumentasi dan presentasi

Menyusun dokumentasi, demo, dan bahan presentasi

16

UAS

Finalisasi dan presentasi project SI-FASKAM

7. Rancangan Fitur Utama

7.1 Login

Mahasiswa memasukkan email/NIM dan password untuk masuk ke aplikasi.

Login
 ├── Input akun
 ├── Input password
 ├── Validasi
 └── Masuk ke Dashboard

7.2 Dashboard

Dashboard menjadi halaman utama yang menampilkan ringkasan pengaduan dan akses menuju fitur utama.

Dashboard
 ├── Buat Pengaduan
 ├── Pengaduan Saya
 ├── Status Pengaduan
 └── Profil

7.3 Form Pengaduan

Form digunakan untuk mengirim laporan fasilitas yang bermasalah.

Data awal yang direncanakan:

Kategori

Judul pengaduan

Deskripsi

Foto

Lokasi

7.4 Status Pengaduan

Status pengaduan dapat dikembangkan menjadi:

Diajukan
   ↓
Diverifikasi
   ↓
Diproses
   ↓
Selesai

8. Rancangan Data Awal

Data utama yang direncanakan pada backend adalah:

users
├── id
├── nama
├── email
├── password
└── role

categories
├── id
└── nama_kategori

pengaduan
├── id
├── user_id
├── category_id
├── judul
├── deskripsi
├── foto
├── latitude
├── longitude
├── status
├── created_at
└── updated_at

Struktur tersebut masih dapat disesuaikan ketika masuk tahap analisis dan implementasi backend.

9. Teknologi yang Direncanakan

Komponen

Teknologi

Mobile

Flutter

Bahasa

Dart

Editor

Visual Studio Code

API

REST API

Backend

Backend SI / server aplikasi

Database

MySQL

Komunikasi data

HTTP + JSON

Fitur perangkat

Kamera, lokasi, notifikasi

Version control

Git + GitHub

10. Bukti Environment

Bukti environment akan disimpan sesuai struktur folder tugas.

Flutter Doctor Sebelum Perbaikan

File: flutter-doctor/sebelum.png



Flutter Doctor Sesudah Perbaikan

File: flutter-doctor/sesudah.png



Aplikasi Flutter Berjalan

File: aplikasi.png



Catatan: Pastikan ketiga file screenshot tersebut benar-benar sudah dimasukkan ke repository sebelum push. Screenshot harus terbaca dengan jelas dan menunjukkan hasil sesuai kebutuhan tugas.

11. Refleksi

Fitur perangkat yang paling relevan untuk SI-FASKAM adalah kamera karena mahasiswa dapat langsung mengambil foto fasilitas yang bermasalah sebagai bukti pengaduan. Fitur lokasi juga penting karena dapat membantu menunjukkan tempat fasilitas yang mengalami kerusakan sehingga laporan lebih mudah ditindaklanjuti. Selain itu, notifikasi dapat digunakan untuk memberi informasi kepada mahasiswa ketika status pengaduannya berubah sehingga pengguna tidak harus terus membuka aplikasi untuk mengecek laporan.

12. Skenario Pengujian Awal

No.

Skenario

Hasil yang Diharapkan

1

Login dengan data benar

Pengguna masuk ke dashboard

2

Login dengan data salah

Muncul pesan kesalahan

3

Form pengaduan belum lengkap

Validasi tampil pada field yang belum diisi

4

Foto berhasil dipilih

Foto tampil pada form pengaduan

5

Lokasi berhasil diambil

Koordinat tersimpan pada data pengaduan

6

Pengaduan berhasil dikirim

Data tersimpan dan status awal tampil

7

Status pengaduan berubah

Status terbaru dapat dilihat mahasiswa

13. Struktur Folder Tugas

Struktur file yang digunakan:

tugas-1/230660221017-Sesi-Pramesti/
├── README.md
├── diagram.png
├── diagram.mmd
├── flutter-doctor/
│   ├── sebelum.png
│   └── sesudah.png
└── aplikasi.png

14. Kesimpulan

SI-FASKAM dirancang sebagai aplikasi mobile yang membantu mahasiswa menyampaikan pengaduan fasilitas kampus secara lebih praktis. Versi awal akan berfokus pada login, pembuatan pengaduan, foto, lokasi, daftar pengaduan, dan pemantauan status, sedangkan proses pengelolaan oleh petugas ditempatkan pada backend SI. Pengembangan dilakukan bertahap sesuai materi perkuliahan sehingga project dapat dimulai dari prototype sederhana dan dilanjutkan sampai integrasi REST API, database, fitur perangkat, testing, dan finalisasi pada UAS.