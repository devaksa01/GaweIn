# Product Requirements Document (PRD)

> Single source of truth for product requirements.
> Focus on WHAT and WHY, not implementation.

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

# Goals (Current Release)

- User bisa login
- Bikin UI UX yang bagus
- User bisa post Gawean(Pekerjaan)
- User bisa ambil Gawean

---

# Non-Goals (Current Release)

- Bos Gawe bisa rate Gawers dan sebaliknya
- User bisa search Gawean
- User bisa chat

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

# Core Flow

## Login Flow

```
→ Buka app
→ Login menggunakan akun google
→ Homepage
```

## Job Post Flow (Setelah Login)

```
→ Buka app
→ Homepage
→ Post Gawean
→ Masukan judul, deskripsi, lokasi, dan biaya
→ Pencet Post, lalu post masuk ke 'Postingan Saya' 
→ Kembali ke homempage
```

## Taking Job Flow (Setelah Login)

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

# Release Plan

## v0.1.0 (MVP)

Goal

...

Features

- [ ]

---

## v0.2.0

Goal

...

Features

- [ ]

---

## v0.3.0

Goal

...

Features

- [ ]

---

## v1.0.0

Goal

...

Features

- [ ]

---

# MVP (Current Release)

## In Scope

-

## Deferred

-

---

# Screens

## Home

Purpose

...

Components

-

Features

-

Empty State

...

---

## Detail

Purpose

...

Components

-

Features

-

Empty State

...

---

## Profile

Purpose

...

Components

-

Features

-

Empty State

...

---

# Functional Requirements

## Authentication

-

---

## Home

-

---

## Search

-

---

## Profile

-

---

# Non-Functional Requirements

## Performance

-

---

## Reliability

-

---

## Security

-

---

## Accessibility

-

---

## Offline Support

-

---

## Compatibility

-

---

# Data Model

## User

Description

Fields

- id
- ...

---

## Job

Description

Fields

- id
- ...

---

## Application

Description

Fields

- id
- ...

---

# Edge Cases

-

---

# Constraints

## Technical

See PROJECT.md

---

## Business

-

---

# Assumptions

-

---

# Dependencies

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