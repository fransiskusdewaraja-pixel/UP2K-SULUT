# SIGAMON — UP2K Sulawesi Utara

Sistem Informasi Gambar, Analisis, dan Monitoring Jaringan Kelistrikan untuk QGIS.

## Rilis terbaru

**v6.17.15 — Perbaikan TM-4X/TR-3 pada Tiang Eksisting**

- Hitung Ulang Konstruksi kini memindai seluruh `TIANG_EKSISTING`, termasuk yang konstruksinya masih kosong.
- JTM yang berujung pada tiang eksisting menghasilkan `TM-4X` pada tiang eksisting tersebut.
- Underbuild JTM/JTR menghasilkan `TM-4X` utama dan `TR-3` bawah pada tiang eksisting yang sama.
- `TR-3` tidak lagi ditempatkan pada tiang rencana tetangga.
- Data `TR-3` otomatis dibersihkan jika underbuild dilepas.
- Gardu dan JTR biasa tetap mengikuti aturan `TR-7`.
- Geometri jaringan dan perhitungan BOQ/kabel tidak diubah.
- Regression suite: 3.428 test lulus, 6 dilewati, 0 gagal.

Patch sumber: [releases/SIGAMON_v6.17.15.patch](releases/SIGAMON_v6.17.15.patch).

Audit: [docs/AUDIT_v6.17.15.md](docs/AUDIT_v6.17.15.md)  
Matriks test: [docs/TEST_MATRIX_v6.17.15.md](docs/TEST_MATRIX_v6.17.15.md)
