# Test Matrix SIGAMON v6.17.12

| Skenario | Hasil wajib |
|---|---|
| Default | Geometri 47,6 → perhitungan 47,6; Otomatis |
| Manual | Geometri 47,6 + manual 50,0 → perhitungan 50,0; Manual |
| Reset | Manual kosong → kembali ke panjang otomatis/geometri |
| Validasi | Nol, negatif, kosong, teks, NaN, dan infinity ditolak |
| Geometry | Edit/reset hanya mengubah atribut; koordinat dan garis tetap |
| Tahap Data | Override Awal, Akhir, dan Realisasi independen |
| KMS/BOQ | Panjang dasar memakai jarak perhitungan |
| Kabel | Formula SUTM/SUTR dan sagging memakai jarak efektif |
| Spreadsheet | Kontrol Kabel menerima hasil BOQ/KMS yang sama |
| Label/Preview | Teks memakai jarak efektif; manual bertanda `*` |
| DXF | Geometry tidak diregangkan oleh override baru |
| Legacy | Tanpa field manual tetap memakai perilaku existing |
