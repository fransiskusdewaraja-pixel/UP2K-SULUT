# SIGAMON — UP2K Sulawesi Utara

Sistem Informasi Gambar, Analisis, dan Monitoring Jaringan Kelistrikan untuk QGIS.

## Rilis terbaru

**v6.17.20 — Underbuild pada JTM Eksisting**

- Pemilih rute membaca graph gabungan JTM tahap terpilih dan JTM Eksisting.
- Jaringan Eksisting tetap read-only; overlay yang dibuat hanya JTR pada layer tahap.
- Jarak (m) input diwariskan dan tetap menjadi satu sumber perhitungan.
- Overlay Existing dihitung sebagai JTR saja sehingga JTM/TM-4X tidak ganda.
- Endpoint tiang Eksisting menerima TR-3 sesuai terminasi route underbuild.
- Scope Judul Proyek, Lokasi Proyek, dan tahap mencegah data lokasi berdekatan tercampur.
- Regression suite: 3.471 test lulus, 6 dilewati, 0 gagal.

Patch sumber: [releases/SIGAMON_v6.17.20.patch](releases/SIGAMON_v6.17.20.patch).

Audit: [docs/AUDIT_v6.17.20.md](docs/AUDIT_v6.17.20.md)  
Matriks test: [docs/TEST_MATRIX_v6.17.20.md](docs/TEST_MATRIX_v6.17.20.md)
