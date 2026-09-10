# AUDIT SIGAMON v6.17.7 — Detail Tarikan Google Spreadsheet

## Implementasi

- Menambahkan sheet `Rencana Awal`, `Rencana Akhir`, dan `Realisasi`.
- Setiap baris detail mewakili satu gawang dan membawa ID stabil dari UUID
  feature, pasangan tiang, atau fallback layer/FID existing.
- Urutan gawang memakai traversal konektivitas; cabang diurutkan natural dan
  semua edge tetap ditulis tepat sekali.
- Underbuild dipisahkan menjadi baris SUTM dan SUTR.
- KMS, sagging, serta tambahan konstruksi ditampilkan sebagai komponen berbeda.
- Tambahan konstruksi SUTM dibebankan pada feature gawang yang membawa atribut
  konstruksinya; tidak digabung ke persen sagging.
- Baris ringkasan menampilkan KMS, tambahan sagging, tambahan konstruksi, dan
  kebutuhan final per klasifikasi.
- Detail memakai presisi sebenarnya dengan format tampilan satu desimal.
  Pembulatan ke atas hanya dilakukan sekali pada total kebutuhan final.
- Status Realisasi hanya dihitung pada baris ringkasan terhadap total Rencana
  Akhir; tidak ada status per gawang.
- `Titik Koordinat` dikelompokkan stabil dalam urutan Rencana Awal, Rencana
  Akhir, lalu Realisasi tanpa mengacak urutan collector di dalam tahap.

## Integritas

- QGIS tetap menjadi sumber geometri dan konektivitas.
- Setting sagging per tahap/per klasifikasi tetap memakai penyimpanan existing.
- Sinkronisasi tetap mencakup seluruh lokasi dalam Judul Proyek aktif.
- Request Google Sheets tetap melalui mekanisme batching existing.
