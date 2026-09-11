# SIGAMON — UP2K Sulawesi Utara

Sistem Informasi Gambar, Analisis, dan Monitoring Jaringan Kelistrikan untuk QGIS.

## Rilis terbaru

**v6.17.17 — Underbuild pada Tiang Eksisting Semua Tahap**

- `TIANG_EKSISTING` menjadi node topologi valid pada Rencana Awal, Rencana Akhir, dan Realisasi.
- Tambah/Hapus Underbuild memproses tiang tahap dan tiang eksisting dalam satu transaksi.
- Endpoint dicocokkan UUID-first dan dibatasi Judul Proyek serta Lokasi Proyek.
- TM-4X utama dan TR-3 bawah dapat tersimpan bersama pada tiang eksisting yang sama.
- Dua terminasi underbuild tetap dihitung sebagai dua kejadian TR-3.
- Tiang eksisting tidak disalin ke layer tahap.
- `Jarak (m)` manual tetap satu sumber untuk jaringan utama dan underbuild.
- Regression suite: 3.448 test lulus, 6 dilewati, 0 gagal.

Patch sumber: [releases/SIGAMON_v6.17.17.patch](releases/SIGAMON_v6.17.17.patch).

Audit: [docs/AUDIT_v6.17.17.md](docs/AUDIT_v6.17.17.md)  
Matriks test: [docs/TEST_MATRIX_v6.17.17.md](docs/TEST_MATRIX_v6.17.17.md)
