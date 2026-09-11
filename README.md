# SIGAMON — UP2K Sulawesi Utara

Sistem Informasi Gambar, Analisis, dan Monitoring Jaringan Kelistrikan untuk QGIS.

## Rilis terbaru

**v6.17.19 — BOQ Topologi Tiang Eksisting**

- TM-4X dihitung satu kali per tiang fisik, bukan satu kali per edge jaringan.
- UUID menjadi identitas utama; fallback ID tetap dibatasi Judul Proyek dan Lokasi Proyek.
- TR-3 underbuild pada tiang eksisting dibaca langsung dari terminasi route aktif.
- Satu route berakhir menghasilkan satu TR-3; route tembus tidak dianggap terminasi.
- Dua route berbeda yang berakhir pada tiang sama menghasilkan dua TR-3.
- Rencana Awal, Rencana Akhir, dan Realisasi mengikuti tahap jaringan yang menempel.
- Regression suite: 3.462 test lulus, 6 dilewati, 0 gagal.

Patch sumber: [releases/SIGAMON_v6.17.19.patch](releases/SIGAMON_v6.17.19.patch).

Audit: [docs/AUDIT_v6.17.19.md](docs/AUDIT_v6.17.19.md)  
Matriks test: [docs/TEST_MATRIX_v6.17.19.md](docs/TEST_MATRIX_v6.17.19.md)
