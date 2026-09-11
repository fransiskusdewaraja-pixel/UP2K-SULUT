# Test Matrix SIGAMON v6.17.18

| Skenario | Expected | Hasil |
|---|---|---|
| Dua lokasi berdekatan dalam desa sama | Graph dan BOQ tetap terpisah | Lulus |
| ID `TS-002` sama pada dua lokasi | Hanya lokasi aktif dihitung | Lulus |
| UUID sama tetapi `id_lokasi` konflik | Ditolak | Lulus |
| UUID benar, metadata lokasi legacy kosong | Tiang existing tetap dikenali | Lulus |
| Tambah Underbuild Rencana Akhir | Tiang existing dapat dipilih/diperbarui | Lulus |
| Rencana Awal dan Realisasi | Aturan node existing tetap sama | Lulus |
| TM-4X pada BOQ | Satu tiang = satu TM-4X per tahap/lokasi | Lulus |
| TM-4X + TR-3 pada satu existing | Tidak saling menimpa | Lulus |
| Hapus Underbuild | TR-3 terkait dibersihkan, TM aktif tetap | Lulus |
| Jarak manual | Nilai `Jarak (m)` bersama tetap dipakai | Lulus |
| Regression penuh | 3.456 lulus, 6 dilewati, 0 gagal | Lulus |
