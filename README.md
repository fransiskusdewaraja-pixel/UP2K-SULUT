# SIGAMON — UP2K Sulawesi Utara

Sistem Informasi Gambar, Analisis, dan Monitoring Jaringan Kelistrikan untuk QGIS.

## Rilis terbaru

**v6.17.22 — Rebuild Tambah Underbuild berbasis topologi**

- Satu resolver membaca Rencana Awal, Rencana Akhir, Realisasi, dan Existing
  berdasarkan Project + Lokasi Proyek + Tahap + UUID, bukan visibility layer.
- Jaringan tahap dan Existing dibangun menjadi satu graph tanpa memutasi
  `DATA_LAYER_MAP` atau menggabungkan graph berdasarkan tebakan koordinat.
- Path JTM deterministik, kandidat bertumpuk dapat dipilih, dan JTR-only tidak
  dapat menjadi shortcut.
- Reapply idempotent; partial Underbuild hanya menulis bentang yang belum ada
  dan memakai kembali identitas rute tunggal agar terminasi/BOQ tetap benar.
- Scope lokasi tanpa ID kanonik dan carrier Existing tanpa identitas stabil
  ditolak sebelum transaksi; `parent_uid` feature kerja tetap provenance.
- Preview menampilkan “Sudah Underbuild” dan “Akan Ditambahkan”, serta bersih
  pada ESC/Tutup/Hapus Hasil.
- Validasi write dan structured transaction logging mencakup rollback.
- Existing tetap read-only sebagai carrier; style solid, aturan TR/BOQ/TM-4X,
  satu Jarak (m), Hapus Underbuild, dan DXF tetap terlindungi regresi.
- Regression suite: 3.519 test lulus, 6 dilewati, 0 gagal.

SHA-256 ZIP instalasi:
`0506f8359b9f66ab14e3688006b1dbe273e21e03b7dde1bc1556b8437a69b9bb`

Patch sumber: [releases/SIGAMON_v6.17.22.patch](releases/SIGAMON_v6.17.22.patch).

Audit: [docs/AUDIT_v6.17.22.md](docs/AUDIT_v6.17.22.md)  
Matriks test: [docs/TEST_MATRIX_v6.17.22.md](docs/TEST_MATRIX_v6.17.22.md)
