<div align="center">

# GaweIn

**Media & komunitas yang menghubungkan pemberi kerja dengan pekerja serabutan.**

![Status](https://img.shields.io/badge/status-early%20development-orange)
![Version](https://img.shields.io/badge/version-v0.1.0--dev-blue)
![License](https://img.shields.io/badge/license-proprietary-lightgrey)
![Platform](https://img.shields.io/badge/frontend-Flutter-02569B?logo=flutter&logoColor=white)
![Backend](https://img.shields.io/badge/backend-Node.js%20%2B%20TypeScript-339933?logo=node.js&logoColor=white)
![Database](https://img.shields.io/badge/database-PostgreSQL-4169E1?logo=postgresql&logoColor=white)

</div>

---

## Tentang

**GaweIn** — dari kata *Gawe* (kerja) — adalah aplikasi cross-platform yang menjadi wadah bagi **Bos Gawe** (pemberi kerja) untuk mem-posting pekerjaan serabutan, dan **Gawers** (pekerja) untuk menemukan serta mengambil pekerjaan tersebut.

Platform jasa digital yang ada saat ini kebanyakan berfokus pada ojek online, sementara ruang untuk pekerjaan serabutan lain (bantu pindahan, bersih-bersih, tukang, dsb.) hampir tidak ada wadahnya. GaweIn hadir untuk mengisi celah itu.

**Visi:** Menjadi media sekaligus komunitas terbesar di Indonesia yang menghubungkan pemberi kerja dengan pekerja serabutan.

## Cara Kerja Singkat

```
Bos Gawe                                   Gawers
   │                                          │
   ├─ Post Gawean (judul, biaya, lokasi, ...)  │
   │                                          ├─ Lihat & pilih Gawean
   │                                          ├─ Tawarkan Diri (bisa nego harga)
   ├─ Terima salah satu Gawers                │
   │                                          ├─ Sedang Gawe (checklist + timer)
   │                                          ├─ Klik Selesai
   ├─ Konfirmasi Selesai ──────────────────────┘
   │
   └─ Gawean & Application → Selesai
```

Koordinasi lanjutan (lokasi presisi, jadwal, dsb.) dilakukan lewat nomor telepon yang dipertukarkan otomatis begitu tawaran diterima — chat & pembayaran dalam aplikasi belum menjadi fokus di versi ini.

## Fitur (MVP v0.1.0)

- [ ] Login via Google OAuth
- [ ] Homepage — list gawean & cek berkala gawean baru
- [ ] Post Gawean — judul, deskripsi, checklist tugas, biaya, lokasi, waktu, lama bekerja
- [ ] Detail Gawean — lihat detail, Tawarkan Diri, nego harga one-shot
- [ ] Postingan Saya — lihat & terima Gawers yang menawarkan diri
- [ ] Sedang Gawe — checklist, timer deadline, kontak Bos Gawe
- [ ] Sedang Memantau — pantau progres Gawers, kontak Gawers
- [ ] Notifikasi — dua arah, Bos Gawe & Gawers
- [ ] Profile Page — edit nama/foto, nomor telepon wajib, logout

Roadmap fitur lengkap (v1.1, v2, dst.) ada di [`docs/FEATURES.md`](docs/FEATURES.md).

## Tech Stack

| Layer | Stack | Alasan |
|---|---|---|
| Frontend | Flutter (Dart) | Performa native & UI konsisten lintas platform, mulai dari Android |
| Backend | Node.js + Express + TypeScript | Arsitektur eksplisit (Route → Controller → Service), type safety untuk state Application |
| Database | PostgreSQL + Prisma ORM | Transaction & row-locking untuk race condition, schema-first migration |
| State Management | Riverpod | Type-safe, testable, polling berkala untuk server-state |
| Auth | Google OAuth (`google_sign_in` + `google-auth-library`) | Login sederhana, backend issue JWT sendiri |
| Storage Media | Cloudinary | CDN foto profil, hindari masalah filesystem ephemeral di hosting |

Detail lengkap & rationale ada di [`docs/PROJECT.md`](docs/PROJECT.md).

## Struktur Repository

```
gawein/
├── frontend/         # Aplikasi Flutter
├── backend/          # REST API (Express + TypeScript + Prisma)
├── shared/           # Kode/tipe yang dipakai lintas frontend-backend
├── infrastructure/   # Konfigurasi deployment & environment
├── design/           # Aset desain (mockup, wireframe)
├── assets/           # Aset statis (ikon, gambar)
├── research/         # Riset produk & teknis
├── prompts/          # Prompt/konteks untuk AI-assisted development
├── scripts/          # Utility scripts
└── docs/             # Dokumentasi proyek (lihat di bawah)
```

> Repo masih di tahap perencanaan — sebagian besar folder di atas masih berupa scaffold kosong.

## Dokumentasi

| Dokumen | Isi |
|---|---|
| [`docs/PRD.md`](docs/PRD.md) | Product Requirements — WHAT & WHY, user stories, flow, data model |
| [`docs/PROJECT.md`](docs/PROJECT.md) | HOW — tech stack, arsitektur, struktur folder |
| [`docs/FEATURES.md`](docs/FEATURES.md) | Checklist fitur per versi |
| [`docs/ROADMAP.md`](docs/ROADMAP.md) | Timeline & milestone |
| [`docs/GLOSSARY.md`](docs/GLOSSARY.md) | Istilah domain (Gawe, Bos Gawe, Gawers, Gawean) |
| [`docs/DECISIONS.md`](docs/DECISIONS.md) | Catatan keputusan arsitektur/desain |
| [`docs/MVP_CHECKLIST.md`](docs/MVP_CHECKLIST.md) | Checklist rilis MVP |
| [`docs/BUGS.md`](docs/BUGS.md) · [`docs/IDEAS.md`](docs/IDEAS.md) · [`docs/LEARNING.md`](docs/LEARNING.md) | Bug tracker, backlog ide, catatan belajar |

## Status Proyek

Proyek masih dalam **tahap perencanaan** (PRD & arsitektur sudah disusun, implementasi kode belum dimulai). Lihat [`docs/ROADMAP.md`](docs/ROADMAP.md) untuk progres terbaru.

## Lisensi

Hak cipta © 2026 AS Adhyaksa. Seluruh hak dilindungi — lihat [`LICENSE`](LICENSE) dan [`NOTICE`](NOTICE). Kode sumber ini adalah milik eksklusif penulis; penggunaan, penyalinan, modifikasi, atau distribusi tanpa izin tertulis dilarang.

---

<div align="center">

Dibuat oleh **AS Adhyaksa** ([@devaksa01](https://github.com/devaksa01))

</div>
