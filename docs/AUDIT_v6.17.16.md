# Audit SIGAMON v6.17.16

## Perubahan

- `JARINGAN_EKSISTING` tidak lagi memakai satu garis ungu.
- JTM/SUTM Eksisting ditampilkan merah solid.
- JTR/SUTR Eksisting ditampilkan biru solid.
- Underbuild Eksisting ditampilkan sebagai JTM merah dan JTR biru sejajar,
  keduanya solid.
- Warna, lebar, dan renderer tipe memakai implementasi bersama dengan jaringan
  Realisasi; perbedaannya dengan Rencana tetap pada pola garis solid/putus-putus.
- Fallback Dashboard mengikuti renderer tipe yang sama apabila clone renderer
  sumber tidak tersedia.

## Batas perubahan

Perubahan hanya menyentuh renderer. Geometri, atribut jaringan, panjang, jarak
manual, label, konstruksi, BOQ, sinkronisasi Spreadsheet, Preview Map, dan DXF
tidak diubah.

## Verifikasi

- Test terarah renderer/preview/label: 58 test lulus.
- Regression penuh: 3.435 test lulus, 6 dilewati, 0 gagal.
