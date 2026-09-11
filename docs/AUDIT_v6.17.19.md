# Audit SIGAMON v6.17.19

## Masalah

1. Ledger menyimpan satu TM-4X untuk setiap edge. BOQ memakai identitas edge,
   sehingga dua edge pada satu tiang eksisting menghasilkan TM-4X dua kali.
2. TR-3 bukan anggota ledger tarikan awal (`TM-4X`/`TR-7`). Tahap pekerjaan
   juga tidak dapat diturunkan dari status fisik tiang eksisting, sehingga
   terminasi underbuild Rencana Akhir dapat hilang dari BOQ.
3. ID seperti `TS-002` dapat berulang pada Lokasi Proyek berdekatan.

## Perbaikan

- Deduplikasi TM-4X memakai identitas tiang fisik. UUID menjadi kunci utama;
  fallback lama memakai Judul Proyek + Lokasi Proyek + ID tiang.
- Indeks jaringan per tahap membawa endpoint UUID/ID, route
  (`id_jalur`/`underbuild_path_id`), status underbuild, dan scope lokasi.
- TR-3 pada existing dihitung dari degree per route: satu segmen route yang
  menempel adalah terminasi; dua segmen route yang sama adalah lintasan; dua
  route berbeda yang berakhir menghasilkan dua TR-3.
- BOQ fullscreen membentuk record TR-3 sementara per status kerja dari
  topologi terpilih. Pembacaan ini tidak memutasi data QGIS.
- Konflik project/id_lokasi ditolak; kedekatan geometri tidak menggantikan
  identitas endpoint.

## Batas Perubahan

Tidak ada perubahan pada rumus kabel, sagging, jarak input, jumlah tiang
fisik, koordinat, spreadsheet, DXF, Preview Maps, ataupun filter F11.

## Verifikasi

- Test fokus BOQ/TM-4X/underbuild: 163 lulus.
- Regression penuh: 3.462 lulus, 6 dilewati, 0 gagal.
