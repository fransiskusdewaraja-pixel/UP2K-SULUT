# SIGAMON — UP2K Sulawesi Utara

Sistem Informasi Gambar, Analisis, dan Monitoring Jaringan Kelistrikan untuk QGIS.

## Rilis terbaru

**v6.17.10 — Hotfix Migrasi Nama Sheet**

- Memperbaiki HTTP 400 ketika workbook masih memiliki tab `KONSTRUKSI TIANG`.
- Tab lama dikenali tanpa membedakan kapitalisasi dan diubah aman menjadi `Konstruksi Tiang` memakai sheetId yang sama.
- SIGAMON tidak lagi mencoba membuat tab duplikat melalui `addSheet`.
- Struktur delapan sheet progress v6.17.9 tetap dipertahankan.
- Regression suite: 3.403 test lulus, 6 dilewati, 0 gagal.

Paket instalasi: `SIGAMON_v6.17.10.zip`.
Patch sumber: [releases/SIGAMON_v6.17.10.patch](releases/SIGAMON_v6.17.10.patch).
