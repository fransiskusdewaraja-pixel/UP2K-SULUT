# SIGAMON — UP2K Sulawesi Utara

Sistem Informasi Gambar, Analisis, dan Monitoring Jaringan Kelistrikan untuk QGIS.

## Rilis terbaru

**v6.17.21 — Topologi Underbuild pada JTM Eksisting**

- Carrier JTM Eksisting tetap merah solid setelah underbuild ditambahkan.
- Overlay tahap hanya menggambar JTR; tidak menggambar ulang JTM Existing sebagai garis putus-putus.
- Konstruksi bawah dihitung dari graph, degree, dan sudut: TR-3 hanya pada terminasi.
- BOQ memuat TR-1/TR-2/TR-3/TR-5 dan tipe lain sesuai hasil topologi, bukan hanya dua endpoint.
- JARINGAN_EKSISTING bukan bukti tarikan awal. TM-4X hanya muncul bila ada tarikan awal JTM Rencana/Realisasi yang nyata.
- Nilai TM-4X/TR-3 stale dari v6.17.20 dibersihkan saat Hitung Ulang.
- Scope Judul Proyek dan Lokasi Proyek tetap mencegah lokasi berdekatan tercampur.
- Regression suite: 3.474 test lulus, 6 dilewati, 0 gagal.

Patch sumber: [releases/SIGAMON_v6.17.21.patch](releases/SIGAMON_v6.17.21.patch).

Audit: [docs/AUDIT_v6.17.21.md](docs/AUDIT_v6.17.21.md)  
Matriks test: [docs/TEST_MATRIX_v6.17.21.md](docs/TEST_MATRIX_v6.17.21.md)
