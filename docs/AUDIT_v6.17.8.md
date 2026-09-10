# Audit SIGAMON v6.17.8

## Hasil implementasi

- Daftar sheet terkelola kini tepat lima dan berurutan: `Kabel`, `Tiang`,
  `KONSTRUKSI TIANG`, `Pindah Lokasi`, `Titik Koordinat`.
- `RINGKASAN KEBUTUHAN`, `Rencana Awal`, `Rencana Akhir`, dan `Realisasi`
  bukan lagi sheet terkelola. Cleanup whitelist menghapus tab lama itu setelah
  kelima tab final berhasil tersedia.
- Kolom `Desa` dihapus dari Kabel, Tiang, KONSTRUKSI TIANG, dan Titik
  Koordinat. Kolom `Desa Asal` dan `Desa Tujuan` dihapus dari Pindah Lokasi.
- Metadata output memakai `Lokasi Proyek`; metadata baris tetap mencakup Judul
  Proyek, Lokasi Proyek, Tahap, Paket, UP3, ULP, Vendor MDU, dan Vendor Jasa.
- Data Desa internal, pencarian/zoom/batas desa, dan fungsi GIS tidak diubah.
- Tahap Data Rencana Awal, Rencana Akhir, dan Realisasi tetap dipertahankan di
  sheet final yang memerlukannya.

## Batas perubahan

Engine BOQ, kebutuhan kabel, KMS tiga fasa, sagging, tambahan konstruksi,
pembulatan CEIL total final, underbuild, konstruksi TM/TR dan TM-4X, koordinat,
ID/status tiang, serta cakupan sinkronisasi seluruh lokasi dalam Judul Proyek
aktif tidak diubah.

## Migrasi workbook lama

Sinkronisasi membangun/menulis lima sheet final lebih dahulu, kemudian
memastikan semuanya tersedia sebelum menghapus seluruh tab di luar whitelist.
Penulisan ulang tabel memakai header dan lebar baris baru sehingga kolom Desa
lama tidak bergeser, tidak menjadi header ganda, dan tidak menyisakan data ekor.
