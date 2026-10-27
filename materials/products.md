# Materi Produk — TimbanganPresisi.com

Ringkasan per produk untuk rework website. Dikumpulkan 2026-10-07 dari source asli
(repo GitHub JTO-Standard & JTO-SmartScan, prd.md + README.md Whale CWO, dan copy
halaman existing `software-jembatan-timbang/index.html`). Repo JTO-Multiitem kosong;
repo Whale JTO Pro tidak tersedia (belum di-push) — materi keduanya murni dari copy
halaman existing + brief yang disetujui user. Lihat "Catatan akurasi" tiap seksi.

---

## Whale JTO Pro

- **Nama resmi produk:** Whale JTO Pro
- **Deskripsi:** Whale JTO Pro adalah varian jembatan timbang untuk operasional skala menengah hingga enterprise yang menggabungkan aplikasi timbang desktop, dashboard monitoring berbasis browser, dan integrasi CCTV dalam satu sistem. Setiap fase timbang (timbang 1 dan timbang 2) otomatis menyimpan snapshot dari kamera yang dipilih dan menghubungkannya langsung dengan nomor tiket transaksi.
- **Fitur kunci:**
  - Live view hingga 4 kamera via RTSP (kamera IP atau kanal NVR, merek agnostik), bisa dibuka dari desktop maupun browser
  - Snapshot otomatis per fase timbang, terhubung ke nomor tiket; foto dibuka dari detail histori transaksi, format JPEG tersimpan lokal di server
  - Dashboard browser internal di jaringan lokal: total transaksi selesai vs pending, total netto harian, riwayat per tiket/kendaraan/customer, export Excel dan cetak PDF
  - Tiga mode transaksi (masuk, keluar, biasa) dengan pending transaction untuk timbang kedua; preview tiket sebelum cetak
  - Multi operator & hak akses, audit trail, dan cetak ulang dengan token yang membedakan ORIGINAL vs COPY
  - Kamera offline TIDAK membatalkan transaksi; foto TIDAK tercetak di tiket; scope jaringan lokal (LAN) tanpa internet; tidak ada recording/playback
- **Target pengguna:** Perusahaan menengah hingga enterprise (pabrik, tambang, logistik) yang butuh dokumentasi visual dan monitoring terpusat atas operasional timbangnya.
- **Catatan akurasi:** Materi di atas dari copy halaman existing + brief yang disetujui user — BELUM TERVERIFIKASI terhadap source kode karena repo JTO Pro belum tersedia. Klaim "database terpusat (PostgreSQL)" dan "multi perangkat terotorisasi" dari tabel perbandingan halaman existing BELUM TERVERIFIKASI di source mana pun selain copy halaman. Sesuai brief: jangan klaim "4 kamera ke-snapshot sekaligus" (jumlah kamera per snapshot BELUM PASTI) dan jangan cantum harga.

---

## Whale JTO Standard

- **Nama resmi produk:** Whale JTO Standard
- **Deskripsi:** Whale JTO Standard adalah aplikasi desktop jembatan timbang (Python, Qt GUI, database SQLite lokal) untuk operasional timbang masuk/keluar/biasa harian. Kekuatan utamanya adalah fleksibilitas label: admin bisa mengubah label mode transaksi dan 8 field transaksi netral tanpa mengubah struktur database maupun logika transaksi.
- **Fitur kunci:**
  - Tiga mode transaksi (masuk, keluar, biasa) dengan perhitungan netto otomatis (netto = bruto − tara); pending transaction untuk timbang kedua
  - 8 field transaksi netral (`field_01`–`field_08`) plus label mode yang bisa diubah admin; form timbang, riwayat, export Excel, dan printout mengikuti label yang tersimpan
  - Master data lengkap: kendaraan, pelanggan/supplier, ekspedisi, jenis truk, barang, driver, operator; import/export master via Excel
  - Koneksi indikator universal via Serial/COM dengan parsing berat memakai `start_index`/`stop_index`; tab `Hardware Link` untuk setting teknis, tab `Timbang` menampilkan angka berat besar untuk operator
  - Template tiket/printout kustom lewat editor layout (posisi, area, alignment, style, token `@FIELD01`–`@FIELD08`); preview dengan tombol Cetak
  - Trial 99 transaksi selesai tanpa lisensi; aktivasi offline berbasis RSA (device ID) — aplikasi berjalan offline penuh tanpa internet
- **Target pengguna:** UKM hingga perusahaan menengah (pabrik, gudang, tambang skala kecil) yang butuh sistem timbang desktop fleksibel dan berjalan offline.
- **Catatan akurasi:** Semua klaim terverifikasi di README.md + docs repo JTO-Standard. Satu gap: daftar merk indikator yang "kompatibel" (AND, Ohaus, CAS, Mettler Toledo, dll) hanya ada di copy halaman existing, tidak dirinci di README repo — BELUM TERVERIFIKASI di source kode.

---

## Whale JTO Smart Scanner

- **Nama resmi produk:** Whale JTO Smart Scanner
- **Deskripsi:** Whale JTO Smart Scanner adalah varian jembatan timbang desktop untuk operasional bervolume tinggi yang mengidentifikasi data transaksi lewat barcode, bukan ketikan manual. Admin membuat data scan dengan format kode yang bisa diatur (contoh `SCN-{seq:05d}`), lalu operator memindai kode tersebut via scanner USB/keyboard wedge saat menimbang.
- **Fitur kunci:**
  - Input transaksi via barcode scanner USB/keyboard wedge; mengurangi input manual dan mempercepat antrian timbang
  - Pembuatan data scan dengan format kode yang bisa diatur plus nomor urut otomatis (contoh `SCN-{seq:05d}`)
  - Cetak label barcode satuan/bulk dengan layout maksimal tiga data scan per halaman
  - Master data scan terpusat plus import/export master via Excel
  - Mewarisi basis Standard: 8 field transaksi fleksibel, mode masuk/keluar/biasa dengan netto otomatis, template tiket kustom, aktivasi offline RSA
  - Koneksi indikator universal Serial/COM; berjalan offline penuh dengan penyimpanan lokal SQLite
- **Target pengguna:** Operasi timbang bervolume tinggi (distributor, logistik, pabrik dengan antrian kendaraan padat) yang butuh input cepat dan konsisten lewat barcode.
- **Catatan akurasi:** Semua klaim terverifikasi di README.md repo JTO-SmartScan. Satu gap: jenis barcode label yang dicetak tidak dirinci di README — BELUM TERVERIFIKASI apakah Code 128/QR; jangan tulis jenis barcode di materi website sampai dikonfirmasi.

---

## Whale JTO Multi Item

- **Nama resmi produk:** Whale JTO Multi Item
- **Deskripsi:** Whale JTO Multi Item adalah varian jembatan timbang untuk kendaraan bermuatan campuran: satu tiket menampung banyak jenis muatan. Netto per item dihitung otomatis dari penimbangan muat bertahap, lengkap dengan harga per kilogram dan subtotal.
- **Fitur kunci:**
  - Satu tiket untuk banyak item
  - Penimbangan muat bertahap
  - Netto per item dari selisih berat
  - Harga/kg & subtotal otomatis
  - Rekap total dalam satu printout
- **Target pengguna:** UKM hingga perusahaan menengah dengan muatan campuran (misalnya distributor atau pabrik yang satu truknya membawa beberapa jenis barang sekaligus).
- **Catatan akurasi:** Repo GitHub JTO-Multiitem KOSONG (size 0 — tidak ada branch berisi kode, 404 di endpoint contents dan zipball). SELURUH materi di atas hanya dari copy halaman existing; tidak ada satu pun fitur yang terverifikasi di source kode. BELUM TERVERIFIKASI: mekanisme "penimbangan muat bertahap", cara hitung netto per item, dan format laporan rekap — detail teknis jangan ditulis di website sampai ada repo/kode atau konfirmasi dari pemilik produk.

---

## Whale CWO

- **Nama resmi produk:** Whale CWO
- **Deskripsi:** Whale CWO adalah aplikasi desktop check weighing (C++/Qt 6, database SQLite lokal, 100% offline) untuk Quality Control dan packaging line. Operator menimbang produk dan aplikasi menilai hasilnya realtime sebagai PASS/UNDER/OVER, lalu setiap transaksi tercatat di database lokal untuk laporan dan cetak struk.
- **Fitur kunci:**
  - Display berat realtime angka besar (±80px) via COM port plus indikator hasil besar UNDER (oranye) / PASS (hijau) / OVER (merah) yang mudah terlihat dari jauh
  - Dua mode transaksi per item: Mode Weighing (target = berat satuan × qty, batas lulus target ± toleransi, auto-save saat PASS stabil ±1,5 detik) dan Mode Qty (tanpa target/status, qty read-only dari database, simpan manual)
  - Master Item CRUD: kode/nama item, berat satuan, qty default, toleransi, min/max weight, shelf life, status, dan mode transaksi
  - Report dengan filter tanggal/item/status/mode, export CSV, print laporan, dan hapus transaksi terpilih
  - Print Layout Editor visual: template struk bebas dengan variabel `@...`, live preview, test print, logo perusahaan, dan barcode Code 128 asli (encoding + checksum benar, font di-bundle)
  - Login role administrator/operator (hash SHA-256; password default wajib diganti saat login pertama); trial 100 transaksi + aktivasi offline RSA
- **Target pengguna:** Packaging line, industri makanan, manufaktur, dan area QC yang butuh penimbangan periksa yang cepat, stabil, dan berjalan 24 jam offline di komputer industri.
- **Catatan akurasi:** Semua klaim terverifikasi di `prd.md` + `README.md` repo cwqt (versi diselaraskan 2026-10-01). Aplikasi sudah di-build dan diklik-test di Windows oleh pemilik (hasil OK). Satu gap: tool KeyGen untuk lisensi RSA belum ditemukan di source — fitur aktivasi offline belum bisa dipakai sampai KeyGen ada.
