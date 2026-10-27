# TimbanganPresisi.com — Source Website

Website statis (HTML + CSS murni, tanpa build step). Rework 2026-10-07:
landing page katalog produk, SEO per halaman produk, desain dark navy
industrial + aksen mint, lolos detektor anti-slop impeccable (0 findings).

## Struktur

```
index.html                  → Home: katalog 5 produk
jto-pro/                    → Detail Whale JTO Pro
jto-standard/               → Detail Whale JTO Standard
jto-smart-scanner/          → Detail Whale JTO Smart Scanner
jto-multi-item/             → Detail Whale JTO Multi Item
whale-cwo/                  → Detail Whale CWO
software-jembatan-timbang/  → Hub kategori JTO (4 varian + perbandingan + FAQ)
software-timbangan/         → Halaman existing (desain baru)
pos-timbangan/              → Halaman existing (desain baru)
barcode-timbangan/          → Halaman existing (desain baru)
integrasi-loadcell/         → Halaman existing (desain baru)
blog/                       → 3 artikel existing (desain baru)
css/style.css               → SATU file CSS untuk semua halaman
img/                        → Gambar per produk (img/jto-pro/, img/jto-standard/, ...)
templates/page-template.html→ Template untuk halaman produk baru
sitemap.xml                 → Daftar URL (update tiap tambah halaman)
```

JANGAN ubah URL halaman yang sudah ada (SEO). `_headers`, `_redirects`,
`robots.txt` jangan dihapus.

## Cara menambah produk baru

Contoh: produk baru "Whale JTO X", halaman di `/jto-x/`.

1. Buat folder `jto-x/`, copy `templates/page-template.html` jadi
   `jto-x/index.html`.
2. Di file itu ganti semua yang bertanda `TODO`:
   - `<title>` (≤60 karakter, ada keyword), meta description (~150 karakter),
     canonical, OG tags
   - H1 = keyword utama produk
   - Deskripsi, fitur kunci, target pengguna, FAQ, screenshot
   - Link WhatsApp: `https://wa.me/6281916364503?text=...` (isi teks
     prefilled sesuai produk, encode spasi jadi `%20`)
   - JSON-LD: ganti nama produk, deskripsi, dan daftar FAQ
3. Taruh screenshot di `img/jto-x/` (JPG, nama huruf kecil, mis.
   `transaksi.jpg`). Di home dan halaman detail, contoh pola gambar:
   `<img src="/img/jto-x/transaksi.jpg" alt="..." loading="lazy">`
4. Tambah kartu produk di `index.html` (copy satu `<article
   class="product-card">` yang sudah ada, ganti isi + link).
5. Tambah URL baru di `sitemap.xml` (copy satu baris `<url>`, ganti `<loc>`
   dan `<lastmod>`).
6. Cek: `npx impeccable detect .` harus 0 findings; pastikan tiap halaman
   tepat SATU `<h1>` dan heading tidak loncat level (h1→h2→h3).

## Kontak CTA

- WhatsApp: `6281916364503` (ganti di semua link `wa.me/...` kalau berubah)
- Email: `info@timbanganpresisi.com`

## Deploy

Upload seluruh isi folder ini (KECUALI folder `.git/` dan file ini kalau
tidak perlu) ke hosting, pertahankan struktur folder. Lalu submit ulang
`sitemap.xml` di Google Search Console.

## Desain

Token warna & komponen ada di `css/style.css` bagian 1 (design token).
Aturan anti-slop: tanpa side-tab, tanpa dark-glow, tanpa emoji di UI,
font IBM Plex Sans (JANGAN ganti ke Inter/Roboto/dkk), kontras teks
minimal 4.5:1. Catatan desain lengkap: `DESIGN.md`.
