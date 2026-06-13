# TimbanganPresisi.com

Static site untuk lead generation - software timbangan digital.

## Deploy ke Cloudflare Pages

### 1. Push ke GitHub
```bash
cd timbanganpresisi
git init
git add .
git commit -m "Initial commit - TimbanganPresisi static site"
git branch -M main
git remote add origin https://github.com/USERNAME/timbanganpresisi.git
git push -u origin main
```

### 2. Connect ke Cloudflare Pages
1. Login ke [Cloudflare Dashboard](https://dash.cloudflare.com)
2. Pilih **Pages** di sidebar
3. Klik **Create a project** > **Connect to Git**
4. Pilih repository `timbanganpresisi`
5. Build settings:
   - **Build command**: (kosongkan, karena static)
   - **Build output directory**: `/` (root)
6. Klik **Save and Deploy**

### 3. Custom Domain
1. Di Cloudflare Pages project, klik **Custom domains**
2. Add domain: `www.timbanganpresisi.com`
3. Karena domain sudah di Cloudflare, DNS otomatis terarah

### Struktur
```
/
├── index.html                    (Homepage)
├── css/style.css                 (Global CSS)
├── software-timbangan/index.html (Landing Page)
├── integrasi-loadcell/index.html (Landing Page)
├── pos-timbangan/index.html      (Landing Page)
├── software-jembatan-timbang/index.html (Landing Page)
├── barcode-timbangan/index.html  (Landing Page)
├── sitemap.xml
├── robots.txt
├── 404.html
├── _redirects                    (Cloudflare redirect rules)
└── _headers                      (Security headers)
```

## Ganti Nomor WhatsApp
Replace semua `6281234567890` dengan nomor WA bisnis Anda.
