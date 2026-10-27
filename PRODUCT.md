# PRODUCT.md — TimbanganPresisi.com

Sales site B2B untuk software timbangan milik dR (Whale Dev). Target visitor:
pemilik/manajer operasional pabrik, tambang, perkebunan, logistik, dan gudang di
Indonesia yang mencari software timbangan lewat Google (SEO organik, tanpa ads).

## Katalog produk (5)

1. **Whale JTO Pro** — jembatan timbang enterprise: aplikasi desktop + dashboard
   browser + CCTV live view hingga 4 kamera via RTSP + snapshot otomatis per fase
   timbang terhubung nomor tiket. Akurasi: jangan klaim "4 kamera ke-snapshot
   sekaligus"; kamera gagal tidak membatalkan transaksi; foto tidak tercetak di
   tiket; scope LAN; tanpa recording/playback; TANPA harga di marketing.
2. **Whale JTO Standard** — jembatan timbang desktop harian (Python/Qt, SQLite
   lokal): timbang masuk/keluar/biasa, 8 field transaksi fleksibel, master data,
   template tiket kustom, trial 99 transaksi, aktivasi offline RSA.
3. **Whale JTO Smart Scanner** — varian barcode: input via scanner USB/keyboard
   wedge, format kode custom + nomor urut, cetak label barcode. Jangan sebut
   jenis barcode label (belum terverifikasi).
4. **Whale JTO Multi Item** — satu tiket untuk muatan campuran: muat bertahap,
   netto per item otomatis, harga/kg + subtotal, rekap satu printout. Repo
   kosong — hanya klaim dari copy halaman existing, jangan karang detail teknis.
5. **Whale CWO** — check weighing QC/packaging line (C++/Qt, SQLite, offline):
   penilaian PASS/UNDER/OVER realtime, 2 mode (Weighing & Qty), master item,
   report + export CSV, Print Layout Editor + barcode Code 128 asli, trial 100
   transaksi.

Struktur web dirancang agar produk baru gampang ditambah: 1 file halaman
`/<slug>/index.html` + 1 kartu di katalog home. Lihat "Cara nambah produk"
di README repo.

## Fakta bisnis

- Kontak CTA: WhatsApp 6281916364503, email info@timbanganpresisi.com.
- Semua varian JTO: koneksi indikator universal via Serial/COM; berjalan offline
  di jaringan lokal tanpa internet.
- Visual marketing: HANYA foto/screenshot asli. Tanpa gambar hasil generate AI.
- Bahasa: Indonesia, santai-profesional. Jujur, tanpa overclaim, tanpa angka
  tanpa sumber.

## Keputusan halaman (brief 2026-10-07, disetujui dR)

- Home = katalog produk langsung. Tanpa hero besar, tanpa trust bar.
- Tiap produk punya halaman detail sendiri (target keyword beda per halaman).
- `/software-jembatan-timbang/` = hub kategori JTO (varian + tabel perbandingan + FAQ).
- URL halaman existing dipertahankan (jaga SEO).
