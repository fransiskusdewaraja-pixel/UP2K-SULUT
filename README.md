# SIGAMON — UP2K Sulawesi Utara

Sistem Informasi Gambar, Analisis, dan Monitoring Jaringan Kelistrikan untuk QGIS.

## Rilis terbaru

**v6.17.11 — Tabel Tiang Selaras dengan Kabel**

- Sheet `Tiang` kini memakai tabel panjang per Lokasi Proyek, klasifikasi/spesifikasi, dan Tahap Data.
- Urutan fase konsisten: Rencana Awal → Rencana Akhir → Realisasi.
- TM dan TR tetap terpisah, dengan target Rencana Akhir, alokasi, deviasi, serta status seperti sheet `Kabel`.
- Identitas Proyek, Lokasi Proyek, Tahap, Paket, UP3, ULP, Vendor MDU, dan Vendor Jasa tersedia pada setiap baris.
- Filter seluruh header, freeze header, dan sinkronisasi seluruh lokasi tetap aktif.
- `Konstruksi Tiang`, BOQ, kabel, sagging, koordinat, F11, Preview Maps, dan DXF tidak diubah.
- Regression suite: 3.406 test lulus, 6 dilewati, 0 gagal.

Paket instalasi: `SIGAMON_v6.17.11.zip`.
Patch sumber: [releases/SIGAMON_v6.17.11.patch](releases/SIGAMON_v6.17.11.patch).
