# Audit SIGAMON v6.17.12

## Hasil implementasi

- `span_distance.py` menjadi satu sumber aturan: manual finite dan lebih dari
  nol mengalahkan panjang otomatis; selain itu panjang existing/geometri tetap
  dipakai.
- Field baru `manual_distance` menyimpan override per feature gawang. Karena
  feature jaringan sudah membawa lokasi dan Tahap Data, nilai Rencana Awal,
  Rencana Akhir, dan Realisasi tidak saling menimpa.
- Detail Tarikan menampilkan Jarak Geometri, Jarak Perhitungan, dan Status
  Jarak serta menyediakan aksi Ubah Jarak dan Kembalikan ke Jarak Geometri.
- Penyimpanan hanya memakai perubahan atribut. Tidak ada operasi perpindahan
  vertex, titik, garis, gardu, koordinat, atau geometry.
- KMS, kebutuhan kabel per gawang, sagging, BOQ, dashboard/rekap, Spreadsheet,
  label peta, dan Preview/PDF memakai jarak perhitungan yang sama.
- Label manual diberi tanda `*`; reset memulihkan nilai otomatis.
- Export DXF tidak menerima target geometry dari field override baru, sehingga
  garis tetap mengikuti bentuk dan koordinat QGIS.

## Kompatibilitas

Project lama tidak memerlukan migrasi manual. Jika `manual_distance` kosong
atau belum ada, urutan field panjang existing dan fallback geometri tetap
berfungsi seperti versi sebelumnya. Formula SUTM tiga fasa, sagging SUTM/SUTR,
tambahan konstruksi, CEIL kebutuhan final, serta seluruh logika tiang tidak
diubah.
