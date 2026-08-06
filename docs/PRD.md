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

## Non-Goals

- Rating (Bos Gawe ↔ Gawers)
- User bisa search Gawean
- User bisa chat

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
→ Masukan judul, deskripsi, lokasi, dan biaya
→ Pencet Post, lalu post masuk ke 'Postingan Saya' 
→ Kembali ke homempage
```

## Taking Gawean Flow (Setelah Login)

```
→ Buka app
→ Homepage
→ Lihat Postingan Gawean
→ Click Gawean Pilihan
→ Baca
→ Click Tawarkan Diri
→ Tunggu Bos Gawe Terima
→ Jika diterima, masuk ke UI sedang bekerja yang berisi list kerjaan yang dipilih, dan timer menuju batas waktu kerjaan
→ Jika sudah selesai, Gawers bisa click selesai
→ Kembali ke homepage
```

## Postingan Saya Flow (Setelah Login)

Description: 'Postingan Saya' berisi gawean yang user post sebagai Bos Gawe, masing-masing post bisa di klik untuk melihat Gawers mana saja yang menawarkan diri untuk melakukan gawean tersebut.

```
→ Buka app
→ Homepage
→ Klik postingan saya
→ Pencet post spesifik
→ Lihat list Gawers yang menawarkan diri
→ Pencet 'Terima'
→ Masuk UI "Sedang Memantau"
→ User sebagai Bos Gawe bisa klik cancel, tunggu hingga waktu selesai, atau tunggu hingga pekerjaan selesai.
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

## Home Page

Purpose: Setelah login, akan selalu menjadi halaman yang ditampilkan ke user saat awal membuka aplikasi, dan jadi tempat untuk melihat semua list gawean yang ada. Setelah semua fitur selesai total idealnya kembali ke home. 

Components: 
-Post gawean 
-List postingan gawean 
-Postingan Saya
-Profile
-Tombol Post Gawean

Features / Requirements: Tampilkan list gawean, terus lakukan cek berkala apakah ada gawean yang baru di post.

Empty State: Saat list postingan kosong, tampilkan 'Belum ada gawean'

## Detail Gawean

Purpose: Agar user dapat melihat detail gawean yang dipilih.

Components: 
- Judul Gawean
- Deskripsi gawean
- Biaya
- Status Gawean (Tersedia/Sudah diambil/)
- Informasi bos gawe
- Tombol ambil gawean

Features / Requirements:
- Informasi detail (judul, deskripsi, biaya, status, informasi bos, dll) tentang job tersebut yang diambil dari database
- Tombol ambil gawean, jika dipencet, requestnya akan masuk ke detail post tersebut di 'Postingan Saya' Bos Gawe

Empty State: -

## Profile Page

Purpose: Untuk melihat atau memodifikasi profile user, dan untuk logout.

Components: Foto profil, nama, akun google yang terkait, tombol logout

Features / Requirements: 
-

Empty State:

## Cross-cutting Edge Cases

> Hanya edge case lintas-screen/lintas-flow.

-

---

# Data Model

## User

- Description: 
- Fields:
  - id
  - ...

## Gawean

- Description:
- Fields:
  - id
  - ...

## Application

- Description:
- Fields:
  - id
  - ...

---

# Non-Functional Requirements

## Performance
-

## Reliability
-

## Security
-

## Accessibility
-

## Offline Support
-

## Compatibility
-

---

# Constraints & Assumptions

## Constraints

Technical: See PROJECT.md
Business: -

## Assumptions
-

## Dependencies
-

---

# Success Metrics

-

---

# Risks

-

---

# Open Questions

-