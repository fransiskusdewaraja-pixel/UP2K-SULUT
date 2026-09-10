# SIGAMON — UP2K Sulawesi Utara

Sistem Informasi Gambar, Analisis, dan Monitoring Jaringan Kelistrikan untuk QGIS.

## Rilis terbaru

**v6.17.12 — Edit Jarak Tanpa Menggeser Jaringan**

- Detail Tarikan menampilkan Jarak Geometri, Jarak Perhitungan, dan Status Jarak.
- Tombol Ubah Jarak menyimpan override per gawang dan per Tahap Data.
- Tombol Jarak Geometri menghapus override dan mengembalikan perhitungan otomatis.
- Edit hanya mengubah atribut `manual_distance`; posisi tiang, koordinat, vertex, dan geometri jaringan tetap.
- KMS, kebutuhan kabel, sagging, BOQ, Spreadsheet, dashboard, serta label memakai satu nilai jarak efektif.
- SUTM tetap tiga fasa dengan sagging 2,5%; SUTR tetap memakai sagging 3%.
- Proyek lama tanpa override tetap bekerja otomatis.
- Regression suite: 3.416 test lulus, 6 dilewati, 0 gagal.

Paket instalasi: `SIGAMON_v6.17.12.zip`.
Patch sumber: [releases/SIGAMON_v6.17.12.patch](releases/SIGAMON_v6.17.12.patch).
