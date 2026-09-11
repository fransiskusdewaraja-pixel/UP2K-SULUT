# Audit SIGAMON v6.17.15

## Akar masalah

Pemindaian penuh tarikan awal hanya memeriksa tiang eksisting yang sudah mempunyai cache TM-4X/TR-7. Tiang eksisting kosong dilewati, sehingga Hitung Ulang tidak pernah dapat membuat TM-4X pertama. Selain itu endpoint bawah pada bentang JTM+JTR underbuild masih dipetakan sebagai TR-7.

## Perbaikan

- Semua `TIANG_EKSISTING` ikut pemindaian Hitung Ulang, termasuk yang konstruksinya masih kosong.
- Endpoint tetap diverifikasi dengan UUID/ID dan posisi fisik maksimal 0,50 m.
- JTM ke tiang eksisting menghasilkan konstruksi utama `TM-4X`.
- JTM+JTR underbuild ke tiang eksisting menghasilkan `TM-4X` utama dan `TR-3` bawah pada tiang eksisting yang sama.
- TR-3 tidak dialihkan ke tiang rencana tetangga.
- Jika underbuild dilepas, TR-3 otomatis lama dibersihkan pada hitung ulang
  berikutnya agar tidak menjadi data konstruksi bawah yang tertinggal.
- Gardu underbuild dan JTR biasa tetap memakai aturan sumber `TR-7`.
- Penulisan anchor berlangsung melalui transaksi existing dan tidak mengubah geometri.

## Verifikasi

- Test terarah: 47 test lulus.
- Regression penuh: 3.428 test lulus, 6 dilewati, 0 gagal.
