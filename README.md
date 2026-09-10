# SIGAMON — UP2K Sulawesi Utara

Sistem Informasi Gambar, Analisis, dan Monitoring Jaringan Kelistrikan untuk QGIS.

## Rilis terbaru

**v6.17.9 — Monitoring Progress Google Spreadsheet**

Struktur final:

1. Kabel
2. Tiang
3. Konstruksi Tiang
4. Pindah Lokasi
5. Titik Koordinat
6. Progress per Lokasi
7. Progress per UP3
8. Progress per Judul Proyek

- Progress UP3 adalah rata-rata seluruh Lokasi Proyek pada kombinasi Judul Proyek + UP3.
- Progress Judul Proyek dihitung langsung dari seluruh lokasi sehingga berbobot menurut jumlah lokasi.
- Kolom Desa tidak diekspor, tetapi data Desa internal QGIS tetap dipertahankan.
- Tab obsolete dan nama lama `KONSTRUKSI TIANG` dibersihkan setelah kedelapan tab tersedia.
- Regression suite: 3.401 test lulus, 6 dilewati, 0 gagal.

Paket instalasi: `SIGAMON_v6.17.9.zip`.
Patch sumber: [releases/SIGAMON_v6.17.9.patch](releases/SIGAMON_v6.17.9.patch).
