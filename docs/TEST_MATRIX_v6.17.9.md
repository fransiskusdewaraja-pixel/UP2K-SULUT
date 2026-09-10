# Test Matrix SIGAMON v6.17.9

| Area | Verifikasi |
|---|---|
| Managed sheets | Delapan tab, urutan final, `Konstruksi Tiang` case-sensitive |
| Migrasi | Nama uppercase lama dan empat tab obsolete dibersihkan setelah delapan tab tersedia |
| Progress lokasi | Satu id lokasi satu row; metadata, status, progress, catatan benar |
| Progress UP3 | Grup Judul Proyek + UP3; jumlah status dan rata-rata lokasi benar |
| Progress proyek | Total UP3 unik non-kosong; rata-rata berbasis seluruh lokasi |
| Weighted aggregation | 10 lokasi 100% + 90 lokasi 0% menghasilkan 10%, bukan 50% |
| Multi-proyek | Nama lokasi/UP3 sama pada dua Judul Proyek tidak tercampur |
| Desa | Tidak muncul pada kedelapan output; data internal tetap tersedia |
| Format | Header frozen, filter aktif, progress tampil satu desimal persen |
| Regresi teknis | BOQ, kabel, tiang, konstruksi, koordinat, tahap, multi-lokasi |
