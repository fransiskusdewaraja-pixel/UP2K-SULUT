# Test Matrix SIGAMON v6.17.19

| Skenario | Expected | Hasil |
|---|---|---|
| Satu existing, dua edge JTM | TM-4X = 1 | Lulus |
| ID existing sama, lokasi berbeda | Masing-masing lokasi tetap terpisah | Lulus |
| UUID cocok, id_lokasi konflik | Koneksi ditolak | Lulus |
| Satu route underbuild berakhir di existing | TR-3 = 1 | Lulus |
| Route underbuild sama melintas existing | TR-3 = 0 | Lulus |
| Dua route underbuild berakhir di existing | TR-3 = 2 | Lulus |
| Rencana Awal/Akhir/Realisasi | Tahap berasal dari jaringan | Lulus |
| Jumlah tiang fisik | Tidak berubah | Lulus |
| Regression penuh | 3.462 lulus, 6 dilewati, 0 gagal | Lulus |
