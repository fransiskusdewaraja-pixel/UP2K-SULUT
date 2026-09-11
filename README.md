# SIGAMON — UP2K Sulawesi Utara

Sistem Informasi Gambar, Analisis, dan Monitoring Jaringan Kelistrikan untuk QGIS.

## Rilis terbaru

**v6.17.18 — Isolasi TM-4X dan Underbuild Antar Lokasi**

- BOQ TM-4X kini terikat pada `id_proyek` dan `id_lokasi`.
- ID tiang seperti `TS-002` yang sama pada dua Lokasi Proyek tidak lagi tercampur.
- Tambah Underbuild mewarisi Lokasi Proyek F11 yang sudah diterapkan.
- Graph menyandingkan tiang dengan endpoint UUID dan scope, bukan kedekatan posisi saja.
- Tiang Eksisting tetap valid pada Rencana Awal, Rencana Akhir, dan Realisasi.
- UUID benar tetap mendukung metadata lokasi legacy yang kosong.
- `Jarak (m)` manual serta logika TM-4X + TR-3 tetap dipertahankan.
- Regression suite: 3.456 test lulus, 6 dilewati, 0 gagal.

Patch sumber: [releases/SIGAMON_v6.17.18.patch](releases/SIGAMON_v6.17.18.patch).

Audit: [docs/AUDIT_v6.17.18.md](docs/AUDIT_v6.17.18.md)  
Matriks test: [docs/TEST_MATRIX_v6.17.18.md](docs/TEST_MATRIX_v6.17.18.md)
