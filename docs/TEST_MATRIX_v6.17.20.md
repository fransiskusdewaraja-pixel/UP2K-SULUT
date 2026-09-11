# Test Matrix SIGAMON v6.17.20

| Skenario | Expected | Hasil |
|---|---|---|
| Lokasi tanpa JARINGAN_RENCANA tetapi memiliki JTM Eksisting | Jalur dapat dipilih | Lulus |
| Graph tahap dan Existing bertemu pada anchor | Node tersambung tanpa lintas lokasi | Lulus |
| Tambah underbuild pada JTM Eksisting | Membuat overlay JTR di layer tahap | Lulus |
| Feature JTM Eksisting sumber | Tetap read-only | Lulus |
| Penerapan ulang sumber+tahap yang sama | Tidak membuat overlay duplikat | Lulus |
| Jarak (m) manual pada carrier | Diwariskan tanpa diganti jarak geometri | Lulus |
| BOQ carrier Existing + overlay JTR | TM-4X = 1, bukan 2 | Lulus |
| Terminasi overlay pada tiang Existing | TR-3 terbaca | Lulus |
| Overlay melintas tiang Existing | Tidak membuat TR-3 palsu | Lulus |
| Lokasi Proyek berdekatan dalam desa sama | Scope tetap terpisah | Lulus |
| Rencana Awal/Akhir/Realisasi | Overlay tersimpan pada tahap pilihan | Lulus |
| Regression penuh | 3.471 lulus, 6 dilewati, 0 gagal | Lulus |
