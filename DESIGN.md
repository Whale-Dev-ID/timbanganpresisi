# DESIGN.md — TimbanganPresisi.com

Rework 2026-10-07; skema terang 2026-10-27 (Tahap Software katalog v2).
Dunia visual: **background mint terang + navy dipertahankan di
header/footer/blok aksen**, nyambung brand Whale JTO Pro.
Mode: Persuade (landing/katalog penjualan).

## Token

- `--bg: #D9F1EF` — background utama (mint terang)
- `--surface: #FFFFFF` — kartu, section alternatif
- `--surface-deep: #071120` — header, footer, panel navy
- `--surface-inset: #E7F5F3` — area media kartu, panel logo
- `--text: #12212E` — teks utama di atas permukaan terang
- `--muted: #47617A` — teks sekunder (±5.6:1 di bg, ±6.5:1 di putih)
- `--accent: #C1EBE9` — mint, aksen di atas navy + tombol primer
- `--link: #0C6E78` — teal gelap, link & aksen di atas permukaan terang
- Teks di atas navy (header/footer): putih + `#C9D8E2` eksplisit per komponen
- Tombol primer: bg `#C1EBE9` + teks `#0A1628` (14.1:1)
- Tombol WA: bg `#25D366` + teks `#052E16` (7.52:1) — teks putih di atas hijau
  hanya 1.98:1 dan gagal WCAG, jadi teksnya hijau sangat gelap
- Elevation: shadow netral ber-offset (`0 18px 44px rgba(0,0,0,.12)`),
  TANPA dark-glow neon

## Tipografi

IBM Plex Sans (Google Fonts, 400/500/600/700) — karakter teknis-industrial
untuk buyer B2B. DILARANG: Inter, Roboto, Fraunces, Geist, Plus Jakarta Sans,
Space Grotesk (daftar font generik AI).

## Aturan anti-slop (ditegakkan, dicek `npx impeccable detect`)

- Tanpa side-tab (border tebal satu sisi kartu) — kartu pakai border 1px seragam
- Tanpa dark-glow / halo berwarna nol-offset
- Tanpa emoji di UI — ikon hanya inline SVG stroke minimal
- Tanpa kicker/eyebrow, tanpa AI beige, tanpa italic serif display
- Satu momen gerak saja: fade-rise `.page-head` saat load + `prefers-reduced-motion`

## Komponen (`css/style.css`, satu file untuk semua halaman)

`.site-header` sticky blur + `.main-nav` + hamburger mobile · `.btn`
`.btn-primary` `.btn-wa` `.btn-ghost` `.btn-sm` · `.badge` · `.page-head`
(H1 = keyword) · `.product-grid` + `.product-card` (media/body/actions) ·
`.feature-list` (centang SVG) · `.table-scroll` + `.compare-table`
(tabular-nums) · `.faq` (details/summary) · `.placeholder-panel` (screenshot
"segera tersedia", dashed border, label eksplisit) · `.wa-float` ·
`.site-footer` 4 kolom · `.skip-link` · `.prose` (artikel blog)

Template referensi: `templates/page-template.html` — header, footer, wa-float,
dan script nav mobile disalin VERBATIM ke semua halaman.

## Detail khas

- `::selection` mint, scrollbar gelap, `:focus-visible` outline mint
- Favicon: `img/favicon.svg` (kotak navy + "TP" mint)
- Canonical SEO: `https://www.timbanganpresisi.com/` (www, ikut halaman existing)
