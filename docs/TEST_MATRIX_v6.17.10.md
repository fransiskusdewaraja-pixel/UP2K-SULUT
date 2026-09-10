# Test Matrix SIGAMON v6.17.10

| Skenario | Hasil wajib |
|---|---|
| Hanya `KONSTRUKSI TIANG` tersedia | Tidak ada `addSheet` untuk nama kanonik |
| Migrasi kapitalisasi | Dua rename berurutan pada sheetId yang sama |
| `Konstruksi Tiang` sudah benar | Tidak ada request rename |
| Setelah rename | Metadata dibaca ulang sebelum struktur/nilai |
| Workbook lengkap | Delapan sheet tetap berurutan dan tidak diduplikasi |
| Regresi | Progress, BOQ, kabel, tiang, koordinat, dan multi-lokasi tetap lulus |
