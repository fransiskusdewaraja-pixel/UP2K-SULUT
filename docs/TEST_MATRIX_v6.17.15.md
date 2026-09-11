# Test Matrix SIGAMON v6.17.15

| Skenario | Expected | Hasil |
|---|---|---|
| JTM biasa berujung TIANG_EKSISTING kosong | TM-4X pada tiang eksisting | Lulus |
| JTM+JTR underbuild berujung TIANG_EKSISTING | TM-4X utama + TR-3 bawah | Lulus |
| Tiang rencana di sebelah endpoint eksisting | Tidak mengambil TR-3 milik endpoint | Lulus |
| Underbuild dari Gardu | TR-7 tetap pada sumber Gardu | Lulus |
| JTR biasa dari TIANG_EKSISTING | TR-7 tetap berlaku | Lulus |
| Pemindaian cache kosong | TIANG_EKSISTING tetap diperiksa | Lulus |
| Underbuild dilepas lalu hitung ulang | TR-3 otomatis lama dibersihkan | Lulus |
| Geometri | Tidak berubah | Lulus |
| Regression penuh | 3.428 lulus, 6 dilewati, 0 gagal | Lulus |
