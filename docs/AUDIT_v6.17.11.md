# Audit SIGAMON v6.17.11

## Ruang lingkup

Perubahan hanya pada penyajian output Google Spreadsheet sheet `Tiang`.
Generator BOQ, kebutuhan kabel, sagging, tambahan konstruksi, koordinat,
`Konstruksi Tiang`, `Pindah Lokasi`, F11, Preview Maps, dan DXF tidak diubah.

## Implementasi

Sheet `Tiang` kini memakai tabel panjang seperti sheet `Kabel`. Setiap
kombinasi Lokasi Proyek, klasifikasi TM/TR, dan spesifikasi menghasilkan tiga
baris berurutan: `Rencana Awal`, `Rencana Akhir`, lalu `Realisasi`.

Setiap baris membawa identitas `Proyek`, `Lokasi Proyek`, `Tahap`, `Paket`,
`UP3`, `ULP`, `Vendor MDU`, dan `Vendor Jasa`. Kolom kontrolnya adalah
`Jumlah Tiang`, `Target Rencana Akhir`, `Alokasi Saat Ini`,
`Saldo / Deviasi`, dan `Status`. Status memakai fungsi serta toleransi existing
yang sama dengan sheet `Kabel`; realisasi yang belum tersedia tetap tampil
`Belum Dihitung` dan bukan nol palsu.

TM dan TR tidak digabung. Sumber tetap snapshot seluruh lokasi dalam Judul
Proyek aktif, bukan lokasi yang sedang dipilih pada F11. Filter bawaan mencakup
seluruh header tabel dan header tetap dibekukan oleh formatter bersama.

## Isolasi perubahan

Konstanta lebar dan indeks kolom `Konstruksi Tiang` dipisahkan dari `Tiang`
agar perubahan bentuk tabel Tiang tidak menggeser format tabel konstruksi.
Tidak ada sheet baru dan tidak ada variasi nama sheet `Tiang`.
