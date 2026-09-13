# Audit SIGAMON v6.17.22 — Rebuild Tambah Underbuild

## Root cause

`UnderbuildRangeDialog` masih memakai engine pengukuran generik yang hanya
mengenal satu `DATA_LAYER_MAP`. Untuk memasukkan jaringan tahap aktif dan
Existing, implementasi lama mengganti mapping global sementara, membangun dua
graph terpisah, lalu menggabungkannya berdasarkan kedekatan koordinat.

Akibatnya:

- Rencana Awal dan Rencana Akhir sama-sama diarahkan lewat status `Rencana`,
  bukan identitas tahap feature yang dipilih;
- kandidat bergantung pada filter/record dashboard F11 yang sedang terlihat;
- Existing baru ditempel setelah graph tahap selesai, sehingga konektivitas
  dan identitas host edge tidak memiliki satu sumber kebenaran;
- `project_key` legacy tidak selalu dinilai oleh predicate scope generik;
- setiap kegagalan parsing feature ditelan oleh `except Exception: continue`,
  kemudian seluruh penyebab dilaporkan sebagai “layer belum memiliki segmen”.

Pesan tersebut karena itu bukan hanya salah teks: collection edge yang dibaca
memang dapat kosong atau tidak terhubung walau jaringan Rencana Awal terlihat.

## Arsitektur baru

`underbuild_topology.py` adalah engine bebas QGIS untuk seluruh tiga tahap.
Engine tersebut menyediakan:

- `UnderbuildContext`: identitas proyek, ID/nama Lokasi Proyek, dan tahap;
- resolver kandidat work + Existing dalam satu operasi;
- aturan scope yang mengutamakan ID/UUID dan tidak menebak record legacy yang
  tidak memiliki identitas proyek;
- graph node/edge dengan UUID host stabil dan fallback spasial toleran hanya
  saat identitas endpoint tidak tersedia;
- pencarian path deterministik, deteksi rute terpendek ambigu, validasi path,
  deduplikasi host/overlay, serta partisi “sudah” vs “akan ditambahkan”.

`UnderbuildRangeDialog` kini hanya menjadi adapter QGIS: membaca feature dari
layer tahap yang dipilih dan `JARINGAN_EKSISTING`, menyerahkannya kepada satu
resolver, menampilkan preview, lalu menulis hasil yang tervalidasi melalui
`ClickTransaction` yang sudah ada.

## Perbaikan perilaku

- Rencana Awal, Rencana Akhir, dan Realisasi memakai engine yang sama dengan
  parameter tahap; tidak ada fallback silang tahap.
- JTM tahap, JTM Existing, dan kombinasi keduanya berada dalam satu graph.
- Existing-only dapat menjadi rute; carrier Existing tidak dimutasi. Overlay
  JTR tahap tetap memakai `parent_uid` host Existing.
- Node ber-UUID berbeda tidak digabung hanya karena koordinatnya dekat. Node
  tanpa identitas dapat memakai fallback spasial dalam tolerance.
- Jalur JTR-only tidak dapat menjadi shortcut pencarian host JTM.
- Reapply pada edge yang sama tidak menulis ulang; partial Underbuild hanya
  menulis edge yang belum tercakup.
- Ringkasan menampilkan panjang “Sudah Underbuild” dan “Akan Ditambahkan”.
- Kandidat klik yang bertumpuk diurutkan deterministik dan meminta pemilihan.
- ESC, Tutup, dan Hapus Hasil membersihkan rubber band, marker, map tool, serta
  cache graph sementara.
- Validasi project/location/stage/node/path/scope dijalankan lagi sebelum
  transaksi. Begin, commit, rollback, exception, provider, run UUID,
  perubahan konstruksi, dan dampak BOQ dicatat sebagai structured log.
- Pesan kosong menyebut tahap dan Lokasi Proyek, bukan nama layer internal.
- Feature rusak dicatat beserta layer/FID/error; tidak lagi dibuang diam-diam.

## Kompatibilitas dan data safety

Tidak ada field, tabel, GeoPackage, UUID, geometri, koordinat, atau setting
user yang dihapus atau di-reset. Tidak diperlukan migrasi schema. Field dan
relasi Underbuild lama tetap dibaca; data legacy ambigu dipertahankan dan
ditolak dari operasi write dengan diagnostic reason, bukan dimodifikasi.

JTM tetap menjadi host. Operasi Existing hanya membuat overlay JTR tahap yang
sudah digunakan versi sebelumnya. Hapus Underbuild, Hitung Ulang Konstruksi,
BOQ, aturan dua terminasi TR-3, deduplikasi TM-4X, satu nilai Jarak (m), DXF,
dan renderer Existing solid tetap memakai engine produksi yang sama dan telah
masuk regression suite.

## Verifikasi

- Test Underbuild baru: 37 lulus, 0 gagal.
- Regression terarah Underbuild/Existing/konstruksi/BOQ/tahap/jarak/DXF/style:
  718 lulus setelah kontrak lama diselaraskan dengan resolver baru.
- Regression penuh: 3.507 lulus, 6 dilewati, 0 gagal.
- `py_compile` dan `git diff --check`: lulus.

Tes otomatis menggunakan engine bebas QGIS dan pemeriksaan kontrak source.
Validasi interaksi klik/render di QGIS desktop tetap direkomendasikan sebagai
smoke test instalasi pada salinan project pengguna sebelum deployment luas.
