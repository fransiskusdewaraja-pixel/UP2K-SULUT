# Test Matrix SIGAMON v6.17.8

| Area | Pemeriksaan |
|---|---|
| Struktur sheet | Tepat lima nama final, urutan tetap, payload kosong tetap lengkap |
| Migrasi | Empat tab obsolete dan tab asing dihapus hanya setelah lima tab final tersedia |
| Header | Tidak ada Desa, Desa Asal, atau Desa Tujuan pada seluruh sheet final |
| Identitas lokasi | Lokasi Proyek dan metadata proyek tetap benar per baris dan per lokasi |
| Multi-lokasi | Kabel, Tiang, dan Titik Koordinat memuat semua lokasi dalam cakupan proyek |
| Tahap Data | Rencana Awal, Rencana Akhir, Realisasi tetap ada dan berurutan |
| Kabel | SUTM, SUTR, KMS, sagging, tambahan konstruksi, dan CEIL final |
| Tiang/konstruksi | TM, TR, underbuild, TM-4X, perubahan desain, status realisasi |
| Metadata organisasi | UP3, ULP, Vendor MDU, Vendor Jasa tidak tertukar |
| Sinkronisasi | Builder, format, filter, batching, cleanup, dan urutan tab |
| Regression | Seluruh `tests/test_*.py` dijalankan sebelum paket rilis dibuat |
