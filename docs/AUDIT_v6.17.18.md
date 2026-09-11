# Audit SIGAMON v6.17.18

## Akar masalah

1. `Tools > Tambah Underbuild` yang dibuka dari canvas utama membuat adapter
   lokasi dengan nilai bawaan `Semua lokasi proyek`. Dua jaringan dari Lokasi
   Proyek berdekatan dapat masuk graph yang sama walaupun F11 sedang menampilkan
   satu lokasi.
2. Label/kandidat tiang ditempelkan ke node jaringan terdekat berdasarkan
   geometri. Tiang eksisting lokasi tetangga dapat terlihat sebagai kandidat.
3. Fallback endpoint lama memakai `id_tiang` seperti `TS-002` tanpa membawa
   `id_lokasi`. ID tersebut sah berulang pada Lokasi Proyek berbeda sehingga
   TM-4X dari lokasi tetangga dapat ikut dihitung.

## Perbaikan

- Tambah Underbuild mewarisi Lokasi Proyek F11 yang sudah diterapkan.
- Penyaringan jaringan mendahulukan `id_lokasi`; nama hanya fallback data lama.
- Setiap node graph menyimpan pasangan endpoint UUID/ID dan scope jaringan.
- Tiang/gardu hanya ditempelkan pada node bila identitas endpoint dan scope
  cocok. Kedekatan geometri hanya verifikasi posisi, bukan identitas.
- UUID endpoint yang sama tetap dapat mengenali tiang lama yang metadata
  lokasinya kosong, tetapi konflik `id_proyek` atau `id_lokasi` selalu ditolak.
- Fallback `id_tiang` diwajibkan berada pada Lokasi Proyek yang sama.
- Indeks koneksi BOQ TM-4X kini membawa `id_proyek`, `id_lokasi`, dan
  `lokasi_proyek` untuk mencegah hitungan lintas lokasi.

## Perilaku yang dipertahankan

- Rencana Awal, Rencana Akhir, dan Realisasi tetap dapat memakai
  `TIANG_EKSISTING` tanpa membuat salinan tiang.
- TM-4X utama dan TR-3 underbuild tetap dapat berada pada tiang yang sama.
- `Jarak (m)` manual tetap menjadi satu nilai bersama untuk gawang utama dan
  underbuild.
- BOQ, Spreadsheet, DXF, Preview Maps, geometri, dan aturan material lainnya
  tidak diubah.

## Verifikasi

- Tes fokus TM-4X/underbuild/lokasi/jarak: 173 lulus.
- Regression penuh: 3.456 lulus, 6 dilewati, 0 gagal.
