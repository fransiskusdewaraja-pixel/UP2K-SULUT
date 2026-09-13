# Test Matrix SIGAMON v6.17.22

| # | Skenario | Expected | Hasil otomatis |
|---:|---|---|---|
| 01 | Rencana Awal A-B-C-D | Path A-D ditemukan pada tahap Awal | Lulus |
| 02 | Rencana Awal planned → Existing | Satu path tersambung | Lulus |
| 03 | Rencana Awal Existing-only | Host Existing dapat dilalui | Lulus |
| 04 | Rencana Akhir + Existing | Resolver hanya menerima tahap Akhir + Existing | Lulus |
| 05 | Realisasi + Existing | Resolver hanya menerima Realisasi + Existing | Lulus |
| 06 | Start Existing, end planned | Endpoint eksplisit tersambung | Lulus |
| 07 | Start planned, end Existing | Endpoint eksplisit tersambung | Lulus |
| 08 | Existing → Existing | Path JTM Existing valid | Lulus |
| 09 | Dua lokasi/proyek berdekatan | Edge proyek tetangga ditolak | Lulus |
| 10 | Tiang Existing dipakai dua proyek | Scope project/location tetap terpisah | Lulus |
| 11 | Reapply edge yang sama | Pending edge kosong; tidak duplicate | Lulus |
| 12 | Partial A-B-C lalu C-D-E | Hanya C-D dan D-E ditulis | Lulus |
| 13 | Hapus Underbuild | JTM/node tetap; konstruksi dihitung ulang | Lulus regresi |
| 14 | Dua route berakhir di node sama | Dua terminasi TR-3 dipertahankan | Lulus regresi |
| 15 | Style JTM/JTR Existing | Merah/biru tetap solid | Lulus regresi |
| 16 | Hitung Ulang pada existing pole | TR berada pada node Existing yang benar | Lulus regresi |
| 17 | BOQ Underbuild/Existing | TR tidak hilang/double; TM-4X tidak palsu | Lulus regresi |
| 18 | Switch Awal → Akhir → Realisasi | Satu resolver membaca tahap pilihan | Lulus |
| 19 | ESC/Tutup saat preview | Rubber band, marker, map tool, cache dibersihkan | Lulus kontrak |
| 20 | Write gagal | `ClickTransaction.abort()` + rollback log | Lulus kontrak/regresi |
| 21 | Bug screenshot Rencana Awal terlihat | `stage_layer` + atribut tahap, bukan mapping status generik | Lulus kontrak |
| 22 | Nama lokasi sama, ID berbeda | ID lokasi menang; kandidat salah ditolak | Lulus |
| 23 | `project_key` tanpa `id_proyek` | Project identity tetap dikenali | Lulus |
| 24 | Legacy tanpa project dan ID lokasi | Tidak ditebak; dicatat `project_missing` | Lulus |
| 25 | Endpoint tanpa UUID/ID | Fallback spasial toleran menghubungkan node | Lulus |
| 26 | UUID endpoint konflik, koordinat sama | Node tidak digabung | Lulus |
| 27 | Dua shortest path sama | Dilaporkan ambigu | Lulus |
| 28 | JTR-only lebih pendek | Tidak menjadi shortcut host JTM | Lulus |
| 29 | Overlay dan host memiliki parent UUID sama | Satu physical host edge | Lulus |
| 30 | Manual Jarak (m) | Satu nilai edge dipakai SUTM/SUTR | Lulus regresi |
| 31 | DXF Underbuild | Offset hanya output DXF, tidak menulis QGIS | Lulus regresi |
| 32 | Lokasi terpilih tanpa ID kanonik | Semua kandidat ditolak sebelum graph/write | Lulus |
| 33 | Dua feature kerja berbagi `parent_uid` | Tetap dua host edge berdasarkan `feature_uuid` | Lulus |
| 34 | Node anonim satu bucket tetapi di luar tolerance | Tidak digabung | Lulus |
| 35 | Node anonim ketiga dekat satu kandidat dalam bucket ambigu | Digabung hanya ke kandidat berjarak valid | Lulus |
| 36 | Underbuild legacy tanpa `underbuild_path_id` | Tetap pending untuk pemulihan identitas | Lulus |
| 37 | Existing legacy tanpa UUID tetapi punya `id_segmen` | Referensi carrier stabil; reapply dapat dideduplikasi | Lulus |
| 38 | Existing tanpa UUID/`uid_objek`/`id_segmen` | Write ditolak sebelum transaksi | Lulus kontrak |
| 39 | Dialog dipakai ulang setelah lokasi F11 berubah | Membaca dashboard sebenarnya, bukan adapter lama | Lulus kontrak |
| 40 | Partial extension dari satu rute | Memakai kembali `underbuild_path_id`; node sambung bukan TR-3 ganda | Lulus |
| 41 | Extension menjembatani dua ID rute | Ditolak sebelum write sebagai ambigu | Lulus |
| 42 | Seluruh regression suite | Tidak ada regresi plugin | 3.519 lulus, 6 skipped |

Catatan: “Lulus kontrak” memverifikasi jalur integrasi source tanpa runtime
QGIS GUI. Smoke test klik/render pada QGIS desktop tetap menjadi langkah
deployment yang disarankan.
