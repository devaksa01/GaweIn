# Product Requirements Document (PRD)

> Single source of truth untuk product requirements (WHAT & WHY).
> Fitur konkret per versi → `FEATURES.md`. Timeline/milestone → `ROADMAP.md`. Section ini tidak menulis ulang keduanya.

---

# Project

Name: GaweIn

Description: Aplikasi cross-platform yang berfungsi sebagai media sekaligus komunitas yang menghubungkan pemberi kerja dengan pekerja serabutan.

Version: v0.1.0

Owner: AS Adhyaksa A.K.A Devaksa01

---

# Vision

Menjadi media sekaligus komunitas terbesar di Indonesia yang menghubungkan pemberi kerja dengan pekerja serabutan, sehingga masyarakat lebih mudah mencari pekerjaan serabutan.

---

# Problem Statement

- Ada orang yang ingin melakukan kerja serabutan tapi tidak tahu mencari di mana
- Ada orang yang ingin memperkerjakan seseorang untuk masalah tertentu namun tidak tahu mencari di mana
- Platform jasa digital yang ada kebanyakan dibuat khusus untuk ojek online, sedangkan kerjaan serabutan lain hampir tidak ada.

---

# Target Users

## Primary

- Pengangguran
- Orang yang ingin bekerja serabutan
- Orang yang ingin bekerja sampingan

## Secondary

- Pelajar yang ingin mendapat uang tambahan

---

# User Stories

- Seorang kepala rumah tangga yang menganggur, ingin mencari pekerjaan serabutan, agar mendapatkan uang untuk menghidupi keluarganya
- Seorang pelajar, ingin mencari pekerjaan serabutan, agar mendapatkan uang jajan tambahan
- Seorang driver ojek online, ingin mencari pekerjaan serabutan lain, agar mendapat uang tambahan

---

# Goals & Non-Goals (Current Release)

> Goal di sini kualitatif (bukan fitur konkret). Untuk checklist fitur, lihat `FEATURES.md` section MVP.

## Goals

- User bisa login dan langsung mulai post/ambil gawean
- UI/UX terasa rapi dan mudah dipakai
- User bisa dapat informasi dari menu notifikasi
- User bisa edit profile, dan logout
- Tugas gawers yang clear dan transparan dengan fitur checklist gawean
- Gawers bisa nego harga pengerjaan gawean saat menawarkan diri

## Non-Goals

- Rating (Bos Gawe ↔ Gawers)
- User bisa search Gawean
- User bisa chat — direncanakan untuk versi berikutnya, MVP pakai pertukaran nomor telepon sebagai gantinya (lihat Profile Page & Sedang Gawe)
- Payment via aplikasi
- Edit profile field selain nama & foto & nomor telepon (misal bio, dll) — direncanakan untuk versi berikutnya

---

# Core Flow

## Login Flow

```
→ Buka app
→ Login menggunakan akun google
→ Homepage
```

## Profile Flow

```
→ Buka App
→ Pencet logo profile
→ Ada informasi profile
→ Kembali ke homepage
```

## Post Gawean Flow (Setelah Login)

```
→ Buka app
→ Homepage
→ Post Gawean
→ Masukan detail informasi Gawean yang diminta
→ Pencet Post, lalu post masuk ke 'Postingan Saya' 
→ Kembali ke homempage
```

## Sedang Gawe Flow (Setelah Login)

```
→ Buka app
→ Homepage
→ Lihat Postingan Gawean
→ Click Gawean Pilihan
→ Baca detail informasi gawean
→ Click Tawarkan Diri
→ Tunggu Bos Gawe Terima
→ Setelah diterima, UI masuk ke Sedang Gawe dengan timer deadline jika ada.
→ Jika sudah selesai, gawers dapat click tombol selesai, status Application (bukan status Gawean) jadi 'Menunggu Konfirmasi Bos Gawe'; UI Gawers tetap di 'Sedang Gawe', belum kembali ke homepage. Jika ada masalah sebelum ini, Gawers bisa click cancel.
→ Setelah Bos Gawe klik 'Terima' (atau 'Cancel'), Gawers baru kembali ke homepage.
```

## Postingan Saya & Sedang Memantau Flow (Setelah Login)

Description: 'Postingan Saya' berisi gawean yang user post sebagai Bos Gawe, masing-masing post bisa di klik untuk melihat Gawers mana saja yang menawarkan diri untuk melakukan gawean tersebut.

```
→ Buka app
→ Homepage
→ Klik postingan saya
→ Pencet post spesifik
→ Lihat list Gawers yang menawarkan diri, termasuk harga yang diusulkan tiap Gawers (bisa beda dari harga asli kalau nego)
→ Pencet 'Terima' pada salah satu Gawers — otomatis menyetujui harga yang diusulkan Gawers itu sebagai harga final
→ Masuk UI "Sedang Memantau", menampilkan nomor telepon Gawers yang diterima untuk koordinasi.
→ User sebagai Bos Gawe bisa klik cancel, tunggu hingga waktu selesai, atau tunggu hingga pekerjaan selesai.
→ Setelah Gawers klik selesai, status Application jadi 'Menunggu Konfirmasi'; Bos Gawe klik 'Terima' untuk finalisasi (Application & Gawean jadi 'Selesai'), atau klik 'Cancel' jika tidak puas (Application jadi 'Dibatalkan', Gawean balik ke 'Tersedia').
→ Kembali ke Homepage
``` 

## Notifikasi flow (Setelah Login)

```
→ Buka app
→ Homepage
→ Klik notifikasi
→ Lihat list notifikasi
→ Klik notifikasi tawaran spesifik, masuk ke detail postingan terkait di 'Postingan Saya' (khusus Bos Gawe)
→ Kembali ke Homepage
```

---

# Screens & Functional Requirements

> Struktur UI + requirement teknis digabung per layar. Nama layar harus sama dengan yang dipakai di Core Flow.

## Login Page

Purpose: Jadi awal semua user baru, user harus login terlebih dahulu untuk mengakses aplikasi, opsi login pada MVP (v0.1.0) hanya memperbolehkan akun google.

Components: 
-Login dengan akun google

Features / Requirements: 
-Google OAuth
-Jika sukses masuk ke homepage
-Jika gagal tampilkan pesan error.

Empty State: -

## Homepage

Purpose: Setelah login, akan selalu menjadi halaman yang ditampilkan ke user saat awal membuka aplikasi, dan jadi tempat untuk melihat semua list gawean yang ada. Setelah semua fitur selesai total idealnya kembali ke home. 

Components: 
-Post gawean 
-List postingan gawean 
-Postingan Saya
-Profile
-Tombol Post Gawean

Features / Requirements: Tampilkan list gawean, terus lakukan cek berkala apakah ada gawean yang baru di post.

Empty State: Saat list postingan kosong, tampilkan 'Belum ada gawean'

## Post Gawean

Purpose: Berupa floating widget atau semacamnya, untuk Bos Gawe mengisi detail dan informasi Gawean untuk di post.

Components:
- Judul Gawean
- Deskripsi gawean
- Checklist gawean
- Biaya
- Lokasi
- Waktu
- Lama bekerja

Features / Requirements:
- Input untuk judul
- Input untuk deskripsi
- Input untuk menambahkan item checklist gawean (list tugas berupa teks, bisa lebih dari satu); checkbox-nya sendiri baru dipakai Gawers saat mengerjakan gawean, lihat 'Sedang Gawe'
- Input untuk biaya (harga awal/tawaran — Gawers masih bisa mengusulkan harga nego saat menawarkan diri, lihat Detail Gawean)
- Selection untuk Lokasi
- Input untuk waktu (tanggal, bulan, tahun)
- Input format 24 jam untuk lama bekerja
- Jika user belum memasukkan nomor telepon di profilenya, user tidak boleh post, dan muncul pop up "Isi nomor telepon terlebih dahulu!", input nomor telpon, tombol silang untuk close pop up, dan tombol isi.

Empty State: 
- Placeholder untuk judul: 'Masukkan judul gawean disini...'
- Placeholder untuk deskripsi: 'Masukkan detail gawean disini...'
- Placeholder untuk biaya: 'Rp ...?'
- Placeholder untuk lokasi: 'Pilih lokasi'
- Placeholder untuk waktu: 'Tanggal, Bulan, Tahun'
- Placeholder untuk lama bekerja: 'Butuh waktu berapa lama?'

## Detail Gawean

Purpose: Agar user dapat melihat detail gawean yang dipilih.

Components: 
- Judul Gawean
- Deskripsi gawean
- Checklist gawean
- Biaya
- Lokasi
- Waktu
- Lama bekerja
- Status Gawean (Tersedia/Sudah Diambil/Selesai)
- Informasi bos gawe
- Tombol Tawarkan Diri

Features / Requirements:
- Informasi detail (judul, deskripsi, biaya, status, informasi bos, dll) tentang job tersebut yang diambil dari database
- Tombol Tawarkan Diri, jika dipencet, requestnya akan masuk ke detail post tersebut di 'Postingan Saya' Bos Gawe
- Tombol Tawarkan Diri membuka form dengan field harga yang default terisi sesuai Biaya gawean, tapi bisa diedit Gawers untuk mengusulkan harga nego (opsional). Nego bersifat one-shot — begitu Bos Gawe klik 'Terima', harga yang diusulkan langsung jadi harga final, tidak ada tawar-menawar balik.
- Jika user belum memasukkan nomor telepon di profilenya, user tidak boleh klik Tawarkan Diri, dan muncul pop up "Isi nomor telepon terlebih dahulu!", input nomor telpon, tombol silang untuk close pop up, dan tombol isi.

Empty State: -

## Profile Page

Purpose: Untuk melihat atau memodifikasi profile user, dan untuk logout.

Components: 
- Foto profil (bisa diedit)
- Nama (bisa diedit)
- Nomor telepon (wajib diisi)
- Akun google yang terkait 
- Tombol edit
- Tombol logout

Features / Requirements: 
- Default nilai foto profil & nama diambil dari akun google saat pertama login.
- User bisa edit nama & foto profil secara manual, tersimpan di database aplikasi (override data google).
- Nomor telepon wajib diisi user; dipakai untuk koordinasi setelah Application diterima, ditampilkan ke lawan pihak di UI 'Sedang Gawe' (Gawers) / 'Sedang Memantau' (Bos Gawe).

Empty State: -

## Sedang Gawe

Purpose: Setelah Gawers mengajukan untuk melakukan pekerjaan dan diterima oleh bos kerja, UI Gawers langsung otomatis berpindah ke UI Sedang Gawe, dan tidak bisa pindah UI sampai Bos Gawe mengkonfirmasi (klik 'Terima' atau 'Cancel') — bukan cuma sampai Gawers klik tombol selesai.

Components:
- Checklist tugas yang harus diselesaikan
- Timer menuju deadline jika ada
- Informasi biaya yang disetujui kedua pihak
- Nomor telepon Bos Gawe
- Tombol selesaikan
- Tombol cancel

Features / Requirements: 
- Tampilkan nomor telepon Bos Gawe yang terkait gawean ini, diambil dari database.
- Mengambil detail informasi gawean dari database
- Menghitung mundur lama kerja yang ditentukan Bos Gawe
- Cek apakah user (sebagai Gawers) punya Application berstatus 'Sedang Dikerjakan' atau 'Menunggu Konfirmasi' — kalau ada, redirect ke UI ini (termasuk saat user logout lalu login lagi). Status kerja di-derive dari Application, bukan disimpan sebagai field terpisah di User.
- Update status Application jadi 'Sedang Dikerjakan' saat mulai kerja, dan status Gawean jadi 'Sudah Diambil'.

Empty State: -

## Notifikasi

Purpose: Informasi yang harus diterima oleh User akan masuk ke sini — baik untuk Bos Gawe (misal ada tawaran baru dari Gawers) maupun Gawers (misal tawarannya diterima, atau Bos Gawe sudah konfirmasi pekerjaan selesai).

Components:
- Judul Notifikasi
- Deskripsi Notifikasi

Features / Requirements:
- Mengambil data notifikasi user dari database
- Tampilkan list notifikasi berdasarkan data tersebut
- Trigger notifikasi ke Bos Gawe saat ada Gawers baru menawarkan diri; diklik akan mengarahkan ke detail postingan terkait di 'Postingan Saya'.
- Trigger notifikasi ke Gawers saat tawarannya diterima Bos Gawe; diklik akan mengarahkan ke UI 'Sedang Gawe'.
- Trigger notifikasi ke Gawers saat Bos Gawe klik 'Terima' atau 'Cancel' setelah Gawers klik selesai.

Empty State: "Belum ada notifikasi nih..."

## Sedang Memantau

Purpose: UI untuk Bos Gawe setelah menerima tawaran seorang gawers untuk mengerjakan gawean yang dipost, bertujuan untuk memantau pekerjaan gawers.

Components:
- Checklist gawean, dan update setiap gawers check salah satu listnya, jadi bisa memantau gawers udah bekerja sampai mana.
- Timer menuju deadline jika ada.
- Informasi biaya yang disetujui (harga final, bisa beda dari harga awal kalau ada nego)
- Nomor telepon Gawers
- Tombol cancel 
- Tombol terima (jika gawers request 'Selesai')

Features / Requirements:
- Mengambil detail gawean dari database
- Ambil data hitung mundur deadline
- Cek berkala request selesaikan gawean dari user
- Tampilkan nomor telepon Gawers yang diterima, diambil dari database.

Empty State: -


## Cross-cutting Edge Cases

> Hanya edge case lintas-screen/lintas-flow.

- **Gawers coba ambil gawean lain saat status "Sedang Gawe" atau "Menunggu Konfirmasi"**: Tidak bisa. UI Gawers tetap terkunci di layar "Sedang Gawe" bahkan setelah Gawers klik "selesai" — baru lepas setelah Bos Gawe klik "Terima" (Application jadi "Selesai") atau "Cancel" (Application jadi "Dibatalkan"). Gawean lain tidak bisa dilihat detail/ditawar sampai saat itu.
- **Bos Gawe pindah UI saat status "Sedang Memantau"**: Berbeda dari Gawers, UI Bos Gawe tidak terkunci. Bos Gawe bebas navigasi ke Homepage, Profile, dll. Untuk memantau progres lagi, tinggal masuk lewat flow "Postingan Saya" → pilih post yang statusnya sedang berjalan.
- **Bos Gawe cancel setelah Gawers klik "selesai"**: Klik "selesai" oleh Gawers mengubah status *Application* (bukan status Gawean) jadi "Menunggu Konfirmasi Bos Gawe". Bos Gawe harus klik "Terima" agar Application & Gawean resmi "Selesai", atau klik "Cancel" kalau tidak puas — Application jadi "Dibatalkan", Gawean balik ke "Tersedia" (kecuali post-nya dihapus).
- **Bos Gawe cancel saat Gawers masih "Sedang Gawe"**: Diizinkan. Application jadi "Dibatalkan oleh Bos Gawe", status Gawean balik ke "Tersedia" supaya Gawers lain bisa ambil — kecuali Bos Gawe juga menghapus post gawean-nya. Karena payment via aplikasi Non-Goal MVP, tidak ada mekanisme kompensasi kerja parsial di dalam aplikasi.
- **Gawers cancel saat status "Sedang Gawe"**: Diizinkan (tombol cancel ada di UI Sedang Gawe). Application jadi "Dibatalkan oleh Gawers", status Gawean balik ke "Tersedia" supaya Gawers lain bisa ambil. Sama seperti kasus dibatalkan Bos Gawe, tidak ada mekanisme kompensasi kerja parsial karena payment via aplikasi Non-Goal MVP.
- **Gawers punya banyak tawaran pending saat salah satunya diterima**: Diizinkan menawarkan diri (status "Menawarkan Diri") ke banyak Gawean sekaligus. Begitu salah satu Application-nya diterima Bos Gawe (jadi "Diterima"), semua Application lain milik Gawers itu yang masih "Menawarkan Diri" otomatis dibatalkan sistem (status jadi "Dibatalkan"), supaya Bos Gawe lain tidak menerima Gawers yang sudah tidak available.
- **Dua Bos Gawe menerima Gawers yang sama secara bersamaan (race condition)**: Sistem harus pastikan cuma satu yang berhasil lewat operasi atomic di database (cek ketersediaan Gawers + update status jadi satu langkah, bukan dua langkah terpisah yang bisa diselipin proses lain). Bos Gawe yang requestnya kalah akan lihat pesan error "Gawers ini baru saja diterima di gawean lain", dan Application-nya otomatis balik ke "Dibatalkan".

---

# Data Model

## User

- Description: Representasi satu akun pengguna, login via Google OAuth. Satu akun bisa berperan sebagai Bos Gawe (saat post gawean) maupun Gawers (saat ambil gawean) — tidak ada field role terpisah.
- Fields:
  - id
  - google_id (identifier dari akun Google yang dipakai login)
  - nama
  - foto_profil_url
  - nomor_telepon

## Gawean

- Description: Representasi satu postingan pekerjaan serabutan yang dibuat oleh seorang Bos Gawe.
- Fields:
  - id
  - bos_gawe_id (relasi ke User)
  - judul
  - deskripsi
  - checklist (list item tugas yang diisi Bos Gawe saat post)
  - biaya
  - lokasi
  - waktu (tanggal mulai kerja)
  - lama_bekerja (durasi, format 24 jam)
  - status (Tersedia / Sudah Diambil / Selesai)
  - created_at (dipakai Homepage untuk cek gawean baru)

## Application

- Description: Representasi satu penawaran/proses kerja seorang Gawers terhadap satu Gawean.
- Fields:
  - id
  - gawean_id (relasi ke Gawean)
  - gawers_id (relasi ke User)
  - status (Menawarkan Diri / Diterima / Sedang Dikerjakan / Menunggu Konfirmasi / Selesai / Dibatalkan)
  - harga_diusulkan (nullable; kosong = pakai Gawean.biaya apa adanya, terisi = harga nego yang diusulkan Gawers. Jadi harga final begitu diterima Bos Gawe)
  - checklist_progress (status checked/unchecked per item checklist Gawean, dipantau Bos Gawe di 'Sedang Memantau')
  - mulai_kerja_at (timestamp saat status jadi 'Sedang Dikerjakan'; jadi basis hitung mundur deadline biar konsisten & tahan logout — lihat Open Questions soal timer)
  - created_at (waktu Gawers menawarkan diri)

## Notification

- Description: Representasi satu notifikasi yang diterima User terkait aktivitas gawean (misal ada tawaran baru).
- Fields:
  - id
  - user_id (relasi ke User penerima)
  - application_id (relasi ke Application terkait, dipakai untuk redirect saat notifikasi diklik)
  - judul
  - deskripsi
  - status (Belum Dibaca / Sudah Dibaca)
  - created_at (urutan list, terbaru duluan)

---

# Non-Functional Requirements

## Performance
- 

## Reliability
-

## Security
- We dont sell user data

## Accessibility
- 

## Offline Support
- No offline support, karena aplikasi ini sangat berkaitan dengan pertukaran data dan informasi dengan server.

## Compatibility
- Direncanakan dapat diakses pada berbagai platform (cross-platform)

---

# Constraints & Assumptions

## Constraints

Technical: See PROJECT.md
Business: -

## Assumptions
- User terhubung dengan internet
- User punya akun google

## Dependencies
- 

---

# Success Metrics

- 100 active user
- 4.5+ rating aplikasi

---

# Risks

- Kejahatan oleh oknum Gawers maupun Bos Gawe yang berniat jahat.
- Gawers bekerja dengan buruk, atau tidak menuntaskan pekerjaan.

---

# Open Questions

- Gimana cara mengatasi oknum yang berencana melakukan hal jahat? resiko yang bisa datang dari gawers atau Bos Gawe.
- Gimana kalau Gawers tidak melakukan pekerjaan dengan baik? 
- Gimana rencana untuk mendapatkan keuntungan dari aplikasi tersebut?
- Gimana rencana sistem pembayaran via aplikasi dan pemotongan biaya aplikasinya? (ide awal: potongan 10% per job — belum bisa diterapkan di MVP karena payment via aplikasi masih Non-Goal)
- Gimana sistem hitung mundur deadline biar konsisten, gabisa di-interrupt, bisa ditampilkan di kedua user, dan ga jadi aneh kalau logout tengah-tengah gawe?