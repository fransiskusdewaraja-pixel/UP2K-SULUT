# Test Matrix SIGAMON v6.17.17

| Skenario | Expected | Hasil |
|---|---|---|
| Rencana Awal hanya tiang eksisting | Semua endpoint valid | Lulus |
| Rencana Akhir hanya tiang eksisting | Semua endpoint valid | Lulus |
| Realisasi hanya tiang eksisting | Semua endpoint valid | Lulus |
| Eksisting + tiang tahap | Satu topologi, tanpa copy tiang | Lulus |
| Terminasi underbuild di eksisting | TR-3 pada konstruksi bawah | Lulus |
| Terminasi SUTM di eksisting | TM-4X pada konstruksi utama | Lulus |
| TM + TR pada satu eksisting | TM-4X dan TR-3 tidak saling menimpa | Lulus |
| Dua underbuild bertemu | Seluruh terminasi dihitung | Lulus |
| UUID endpoint bertentangan | Tidak fallback ke ID/posisi | Lulus |
| Proyek/lokasi berbeda | Tidak tercampur walau berhimpit | Lulus |
| Hapus Underbuild | TR terkait hilang; TM aktif dipertahankan | Lulus |
| Hitung Ulang Konstruksi | Existing tetap dipindai | Lulus |
| Jarak manual utama + underbuild | Satu nilai `Jarak (m)` tersimpan | Lulus |
| Save/reload identitas | Tidak ada copy; UUID sumber tidak diubah | Lulus |
| Regression penuh | 3.448 lulus, 6 dilewati, 0 gagal | Lulus |
