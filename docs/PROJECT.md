# Project Documentation

> Single source of truth untuk project development.
> Fokus pada HOW project ini dikembangkan. Untuk WHAT & WHY (nama, deskripsi produk, goals) → `PRD.md`.

---

# Overview

Name: GaweIn *(lihat PRD.md untuk deskripsi produk)*

Repository: https://github.com/devaksa01/gawein

---

# Tech Stack

## Frontend

- **Flutter (Dart)** — performa native & UI konsisten lintas platform. Fokus Android dulu untuk MVP, tapi arsitekturnya memungkinkan expand ke iOS/Web nanti tanpa rewrite besar.

## Backend

- **Node.js + Express + TypeScript** — REST API. Express dipilih karena minim "magic", gampang dipahami step-by-step (routing → controller → service). TypeScript buat type safety, khususnya di state Application (Menawarkan Diri/Diterima/Sedang Dikerjakan/dst.) yang rawan bug kalau cuma pakai string biasa.

## Database

- **PostgreSQL** — relational, support transaction & row-locking (`SELECT ... FOR UPDATE`) untuk race condition (misal dua Bos Gawe menerima Gawers yang sama secara bersamaan — lihat Cross-cutting Edge Cases di `PRD.md`).
- **Prisma ORM** — schema-first, migration otomatis, lebih ramah pemula dibanding raw SQL tapi tetap mengajarkan konsep relasi & query.

## State Management

- **Riverpod** — type-safe, testable, dipakai untuk server-state termasuk polling berkala (gawean baru di Homepage, notifikasi) via `FutureProvider`/`AsyncNotifier`.

## Local Storage

- **flutter_secure_storage** — menyimpan JWT token di device supaya user tetap login antar sesi. Tidak ada local data storage lain karena PRD eksplisit "No offline support".

## Services

- **Google OAuth** — `google_sign_in` (client, Flutter) mengambil token Google → dikirim ke backend → diverifikasi via `google-auth-library` (server) → backend issue JWT sendiri untuk session.
- **Cloudinary** — storage & CDN untuk foto profil (upload, auto-resize/compress). Menghindari masalah filesystem ephemeral kalau backend di-deploy ke platform seperti Render/Railway.

## Development Tools

- TBD

---

# Architecture

## Architecture Pattern

- **Backend**: Layered REST API — Route → Controller → Service → Repository (Prisma).
- **Frontend**: Feature-first modular structure (lihat Folder Structure).

## Folder Structure

Frontend (Flutter), feature-first — dikelompokkan per domain (selaras dengan Data Model di `PRD.md`), bukan per tipe file, supaya kode yang berhubungan sama fitur ngumpul di satu tempat:

```
lib/
├── core/                    # shared, dipakai lintas fitur
│   ├── config/              # theme, constants, env
│   ├── network/             # dio client, interceptors (JWT attach, dsb)
│   ├── router/              # navigation setup
│   └── widgets/             # reusable widget generik (button, loading, dsb)
│
├── features/
│   ├── auth/                # Login Page
│   ├── gawean/               # Homepage, Post Gawean, Detail Gawean
│   ├── application/          # Postingan Saya, Sedang Gawe, Sedang Memantau
│   ├── profile/               # Profile Page
│   └── notification/          # Notifikasi
│       # tiap feature folder: screens/, widgets/, providers/, models/
│
└── main.dart
```

Backend folder structure: belum didiskusikan detail, TBD saat mulai implementasi.

## Navigation Strategy

- TBD

## State Management Strategy

- Riverpod providers per-feature. Server-state (list gawean, notifikasi) di-refresh berkala (polling) sesuai requirement "cek berkala" di `PRD.md` — bukan real-time/WebSocket, karena chat & update real-time eksplisit Non-Goal MVP.

## Data Flow

- Flutter (Riverpod) → REST API (Express) → Prisma → PostgreSQL.
- **Auth**: Google Sign-In (client) → token dikirim ke backend → verifikasi via `google-auth-library` → backend issue JWT → disimpan di `flutter_secure_storage` → dilampirkan di header tiap request berikutnya.
- **Upload foto profil**: belum diputuskan — apakah client upload langsung ke Cloudinary (signed upload dari backend) atau lewat backend sebagai proxy. Perlu didiskusikan lebih lanjut.

---

# Development Workflow

1. Read PRD
2. Read WORKS
3. Implement
4. Test
5. Review
6. Commit
7. Update documentation

---

# Coding Standards

Naming

Formatting

Error Handling

Logging

Comments

Git Convention

---

# Documentation

PRD.md

ROADMAP.md

WORKS.md

DECISIONS.md

API.md

TESTING.md

RELEASE.md

---

# References

External documentation

Design files

Figma

API Docs

---

# Notes