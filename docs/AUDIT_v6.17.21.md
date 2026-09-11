# Audit SIGAMON v6.17.21

## Masalah

Overlay underbuild pada JTM Eksisting sebelumnya diperlakukan seperti
underbuild komposit biasa. Akibatnya renderer menggambar ulang garis merah
Rencana secara putus-putus di atas carrier merah solid. Sinkronisasi tarikan
awal juga memindai `JARINGAN_EKSISTING`, sehingga setiap TS sepanjang carrier
dianggap sumber JTM dan diberi `TM-4X`. Konstruksi bawah ditulis `TR-3` per
endpoint ruas, sedangkan BOQ hanya menurunkan dua terminasi route; label dan
BOQ menjadi tidak konsisten.

## Perbaikan

- Overlay `JTR UNDERBUILD PADA JARINGAN EKSISTING` dirender sebagai garis JTR
  biru saja. Garis JTM merah tetap berasal dari `JARINGAN_EKSISTING`, sehingga
  selalu solid dan tidak digambar ulang sebagai garis Rencana.
- Evaluator khusus memproses seluruh node `TIANG_EKSISTING` pada route overlay
  sebagai graf TR. Endpoint, lintasan, belokan, cabang, dan perempatan dihitung
  dari degree serta sudut melalui tabel SK-GM yang sama dengan JTR biasa.
- `TR-3` hanya dipaksakan bila sebuah route benar-benar berterminasi pada node.
  Node tembus tidak lagi menerima `TR-3` dari masing-masing ruas.
- BOQ membentuk record tahap untuk seluruh konstruksi bawah route existing:
  terminasi dari route, dan tipe node lainnya dari hasil evaluator topologi.
- Pemindai tarikan awal hanya membaca `JARINGAN_RENCANA` dan
  `JARINGAN_AKTUAL`. Carrier existing dan overlay JTR existing tidak dapat
  menciptakan `TM-4X`.
- `TM-4X` hanya dipertahankan bila ada edge JTM kerja yang benar-benar mulai
  dari tiang existing. Nilai `TM-4X`/ledger stale dari versi sebelumnya
  dibersihkan otomatis ketika Hitung Ulang dijalankan.
- Scope tetap dibatasi Judul Proyek dan Lokasi Proyek/ID lokasi; lokasi yang
  berdekatan dalam desa yang sama tidak dapat bergabung.

## Batas Perubahan

Tidak ada perubahan pada geometri, Jarak (m) input, perhitungan kabel, sagging,
tambahan konstruksi, CEIL, koordinat, Google Spreadsheet, DXF, Preview Maps,
atau filter operasional F11.

## Verifikasi

- Test fokus underbuild/topologi/konstruksi/DXF: 131 lulus, 0 gagal.
- Regression penuh: 3.474 lulus, 6 dilewati, 0 gagal.
