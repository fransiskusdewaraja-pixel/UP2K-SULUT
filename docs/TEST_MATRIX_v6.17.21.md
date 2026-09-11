# Test Matrix SIGAMON v6.17.21

| Skenario | Expected | Hasil |
|---|---|---|
| Overlay JTR pada JTM Eksisting Rencana | Merah carrier tetap solid; hanya JTR overlay mengikuti style tahap | Lulus |
| TS dilalui carrier Eksisting tanpa tarikan JTM kerja | Tidak mendapat TM-4X | Lulus |
| JTM Rencana/Realisasi benar-benar mulai dari TS | TM-4X tercatat satu kali | Lulus |
| Route underbuild berterminasi | Endpoint mendapat TR-3 | Lulus |
| Route underbuild melintas node | Bukan TR-3 per ruas; memakai degree+sudut | Lulus |
| Route berbelok/bercabang | Rekomendasi TR mengikuti tabel SK-GM | Lulus |
| BOQ underbuild pada existing | Memuat terminasi dan seluruh tipe node topologis | Lulus |
| Nilai TM-4X/TR-3 stale v6.17.20 | Dibersihkan/dihitung ulang dalam transaksi | Lulus |
| Dua lokasi berdekatan dalam desa sama | Tidak tercampur | Lulus |
| Jarak (m) utama dan underbuild | Tetap satu nilai input | Lulus |
| Rencana Awal/Akhir/Realisasi | Tetap terisolasi per tahap | Lulus |
| Regression penuh | 3.474 lulus, 6 dilewati, 0 gagal | Lulus |
