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
- Reapply idempotent; partial Underbuild hanya menulis bentang yang belum ada.
- Preview menampilkan “Sudah Underbuild” dan “Akan Ditambahkan”, serta bersih
  pada ESC/Tutup/Hapus Hasil.
- Validasi write dan structured transaction logging mencakup rollback.
- Existing tetap read-only sebagai carrier; style solid, aturan TR/BOQ/TM-4X,
  satu Jarak (m), Hapus Underbuild, dan DXF tetap terlindungi regresi.
- Regression suite: 3.507 test lulus, 6 dilewati, 0 gagal.

Patch sumber: [releases/SIGAMON_v6.17.22.patch](releases/SIGAMON_v6.17.22.patch).

Audit: [docs/AUDIT_v6.17.22.md](docs/AUDIT_v6.17.22.md)  
Matriks test: [docs/TEST_MATRIX_v6.17.22.md](docs/TEST_MATRIX_v6.17.22.md)
