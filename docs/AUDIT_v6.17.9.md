# Audit SIGAMON v6.17.9

## Struktur final

Workbook dikelola dalam urutan: Kabel, Tiang, Konstruksi Tiang, Pindah
Lokasi, Titik Koordinat, Progress per Lokasi, Progress per UP3, dan Progress
per Judul Proyek. Nama lama `KONSTRUKSI TIANG` berada di luar whitelist dan
dibersihkan setelah tab pengganti berhasil tersedia.

Empat tab detail/ringkasan lama tetap tidak dikelola. Seluruh output tidak
memiliki kolom Desa, Desa Asal, atau Desa Tujuan; fungsi Desa internal QGIS
tidak diubah.

## Progress

`progress_location_records()` menjadi satu-satunya sumber ketiga sheet.
Identitas unik memakai Judul Proyek/id proyek dan Lokasi Proyek/id lokasi.
Nilai Tahap Pekerjaan, Status, progress, catatan, vendor, dan timestamp dibaca
dari master lokasi existing.

Progress UP3 adalah rata-rata seluruh lokasi dalam kombinasi Judul Proyek +
UP3. Progress Judul Proyek dihitung langsung dari seluruh lokasi, bukan
rata-rata antar-UP3, sehingga berbobot otomatis menurut jumlah lokasi.

## Batas perubahan

BOQ, SUTM/SUTR, KMS, sagging, tambahan konstruksi, CEIL kebutuhan final,
underbuild, TM/TR, TM-4X, koordinat, tahap gambar, dan cakupan sync seluruh
lokasi pada Judul Proyek aktif tidak diubah.
