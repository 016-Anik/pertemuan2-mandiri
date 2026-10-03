# TM-1 — Peta Routing Pribadi

Entity: Peminatan

## Base API

BASE=https://silab.ft.unira.ac.id/api/v1

## Peta Routing

| METHOD + API | SvelteKit File | ATLAS SPA | Flutter name + args | US |
|---|---|---|---|---|
| GET /api/v1/peminatan | routes/peminatan/+page.svelte | /peminatan | getPeminatan() | US-01 |
| GET /api/v1/peminatan/:id | routes/peminatan/[id]/+page.svelte | /peminatan/:id | getPeminatanDetail(id) | US-02 |
| POST /api/v1/peminatan/pilih | routes/peminatan/pilih/+page.svelte | /peminatan/pilih | selectPeminatan(data) | US-03 |
| GET /api/v1/peminatan/statistik | routes/peminatan/statistik/+page.svelte | /peminatan/statistik | getPeminatanStatistik() | US-04 |
| GET /api/v1/peminatan/:id/mahasiswa | routes/peminatan/[id]/mahasiswa/+page.svelte | /peminatan/:id/mahasiswa | getMahasiswaByPeminatan(id) | US-05 |

## Authorization

- US-01: authorize(Mahasiswa, Kaprodi, Tendik)
- US-02: authorize(Mahasiswa, Kaprodi, Tendik)
- US-03: authorize(Mahasiswa)
- US-04: authorize(Kaprodi, Tendik)
- US-05: authorize(Kaprodi, Tendik)

## Keterangan

- `[id]` digunakan untuk route data peminatan spesifik (misal: ID atau Kode peminatan BI / SA).
- `pilih` digunakan untuk route form/proses pemilihan peminatan oleh mahasiswa.
- `statistik` digunakan untuk route rekap statistik jumlah mahasiswa per peminatan.
- `GET` digunakan untuk mengambil data peminatan, rincian, statistik, dan daftar mahasiswa.
- `POST` digunakan untuk menyimpan pilihan peminatan mahasiswa.
- Semua endpoint menggunakan prefix `/api/v1`.
- ID peminatan yang digunakan pada route `[id]` masih berupa parameter dan belum menggunakan ID asli.