# Audit SIGAMON v6.17.17

## Akar masalah

`Tambah Underbuild` sebelumnya hanya membuka `TIANG_RENCANA` atau
`TIANG_AKTUAL` sesuai tahap jaringan. `TIANG_EKSISTING` terlihat pada peta,
tetapi tidak ikut dalam transaksi titik sehingga tidak memperoleh TR-3 dan
sinkronisasi TM-4X pada saat underbuild diterapkan.

## Perbaikan

- Helper pusat `topology_layer_names()` mengembalikan layer tiang tahap aktif
  bersama satu layer fisik `TIANG_EKSISTING`.
- Berlaku generik untuk Rencana Awal, Rencana Akhir, dan Realisasi.
- Picker rentang menampilkan node/label tiang serta gardu eksisting bersama
  node tahap aktif.
- Tambah dan Hapus Underbuild menjalankan satu transaksi atas jaringan,
  tiang tahap, dan tiang eksisting.
- Endpoint dicocokkan UUID-first. ID tiang hanya menjadi fallback jika salah
  satu sisi benar-benar belum mempunyai UUID; UUID yang bertentangan ditolak.
- Scope Judul Proyek dan Lokasi Proyek wajib sama. Garis yang sekadar berhimpit
  dari scope lain tidak boleh ikut terbaca.
- Tiang eksisting tidak pernah disalin ke layer tahap.
- Pada underbuild JTM/JTR, konstruksi utama TM-4X dan konstruksi bawah TR-3
  ditulis independen pada tiang eksisting yang sama.
- Dua jalur yang berterminasi pada satu tiang tetap menghasilkan dua kejadian
  TR-3 sesuai ledger topologi.
- Penghapusan underbuild menghitung ulang titik tahap dan titik eksisting;
  TM-4X tetap ada selama jaringan JTM masih menempel.

## Yang dipertahankan

- `Jarak (m)` manual tetap prioritas dan dipakai bersama oleh jaringan utama
  serta underbuild pada gawang yang sama.
- Geometri, BOQ, Google Spreadsheet, Preview Maps, DXF, Foto, F11, renderer,
  dan aturan material tidak diubah.
- Data lama tanpa UUID masih dapat memakai ID endpoint, lalu geometri sebagai
  fallback hanya bila endpoint memang tidak membawa identitas.

## Verifikasi

- Tes terarah tahap, underbuild, existing connectivity, dan jarak: lulus.
- Regression penuh: 3.448 tes lulus, 6 dilewati, 0 gagal.
