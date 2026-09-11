# Audit SIGAMON v6.17.20

## Masalah

Dialog Tambah Underbuild hanya membangun graph dari `JARINGAN_RENCANA` atau
`JARINGAN_AKTUAL`. Ketika lokasi hanya mempunyai JTM Eksisting, dialog berhenti
dengan pesan bahwa layer Rencana belum mempunyai segmen. Selain itu, bila
geometri existing disalin tanpa klasifikasi khusus, overlay dapat dianggap JTM
baru dan menyebabkan TM-4X/BOQ terhitung dua kali.

## Perbaikan

- Graph pemilihan menggabungkan JTM tahap terpilih dengan
  `JARINGAN_EKSISTING` pada Judul Proyek dan Lokasi Proyek yang sama.
- Node berhimpit digabung secara topologis sehingga rute dapat melewati anchor
  bersama tanpa memakai jaringan dari lokasi berdekatan.
- Segmen Existing tidak pernah dimutasi. Satu overlay JTR bertahap dibuat pada
  `JARINGAN_RENCANA` atau `JARINGAN_AKTUAL` dengan `parent_uid` segmen sumber.
- Penerapan ulang pada sumber dan tahap yang sama bersifat idempotent.
- Seluruh atribut jarak diwariskan; `manual_distance`/Jarak (m) input tetap
  menjadi sumber utama dan geometri tidak diubah.
- Overlay existing diklasifikasikan sebagai JTR-underbuild saja. JTM carrier
  tetap dibaca dari layer Existing, sehingga BOQ memperoleh tepat satu TM-4X
  dan terminasi bawah memperoleh TR-3 tanpa menggandakan kebutuhan JTM.
- Rencana Awal, Rencana Akhir, dan Realisasi tetap terpisah oleh `tahap_data`.

## Batas Perubahan

Tidak ada perubahan pada rumus kabel, sagging, tambahan konstruksi, CEIL,
jumlah tiang fisik, koordinat, Google Spreadsheet, DXF, Preview Maps, atau
filter operasional F11.

## Verifikasi

- Test fokus BOQ/TM-4X/underbuild/tahap: 235 lulus, 0 gagal.
- Regression penuh: 3.471 lulus, 6 dilewati, 0 gagal.
