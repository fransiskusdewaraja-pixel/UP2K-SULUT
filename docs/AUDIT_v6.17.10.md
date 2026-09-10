# Audit SIGAMON v6.17.10

## Masalah

Google Sheets memperlakukan `KONSTRUKSI TIANG` dan `Konstruksi Tiang`
sebagai nama yang sama, sedangkan pemeriksaan metadata SIGAMON sebelumnya
case-sensitive. Tab lama dianggap hilang dan proses mencoba `addSheet`, lalu
Google menolak request sebagai nama duplikat.

## Perbaikan

Sebelum menambah atau memformat sheet, sinkronisasi kini mencari padanan nama
secara case-insensitive. Tab lama diubah menggunakan sheetId yang sama melalui
rename berurutan `nama sementara → Konstruksi Tiang`. Metadata kemudian dibaca
ulang sebelum pembentukan struktur dan penulisan nilai.

Tidak ada tab baru, data lama tidak diduplikasi, dan cleanup tetap hanya
berjalan setelah delapan sheet final tersedia. BOQ, material, koordinat,
progress, tahap gambar, dan data internal QGIS tidak berubah.
