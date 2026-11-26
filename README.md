# BARMODS STORE — Comic VPN Creator

Website create & trial akun VPN (**SSH, VMess, VLESS, Trojan, Shadowsocks**) bertema komik dengan navigasi gelembung, struktur super ringkas (HTML + CSS + JS digabung di `index.html`), dan siap deploy ke **GitHub → Vercel**.

## Struktur Folder

```text
barmods-vpn/
├── index.html        # Halaman utama (HTML + CSS + JS jadi 1 file)
├── api/
│   └── create.js     # Serverless API Vercel (baca domain & API auth dari .env)
├── vercel.json       # Konfigurasi Vercel
├── package.json      # Metadata Node.js 18+ (tanpa dependency ribet)
├── .env.example      # Contoh variabel environment
└── .gitignore        # Melindungi .env agar tidak ter-upload ke GitHub
```

## Cara Deploy ke GitHub & Vercel

1. **Upload ke GitHub**
   - Ekstrak folder `barmods-vpn`, lalu push ke repository GitHub baru:
     ```bash
     git init
     git add .
     git commit -m "Initial commit BARMODS VPN"
     git branch -M main
     git remote add origin https://github.com/USERNAME_KAMU/barmods-vpn.git
     git push -u origin main
     ```
2. **Deploy di Vercel**
   - Masuk ke [vercel.com](https://vercel.com), klik **Add New → Project**, lalu pilih repository `barmods-vpn`.
   - Sebelum klik **Deploy**, buka bagian **Environment Variables** dan tambahkan:
     - `VPN_DOMAIN` = domain VPS kamu (contoh: `sg1.domainkamu.com`)
     - `VPN_AUTH` = API key / auth panel port `5888` kamu
     - `VPN_CLOUDFRONT` = `-` (atau domain CloudFront jika pakai)
     - `VPN_API_PORT` = `5888`
     - `VPN_SERVER_NAME` = `BARMODS VIP` (opsional)
   - Klik **Deploy** dan selesai!

> **Multi-Server (Opsional):** Jika punya lebih dari 1 server, cukup tambahkan variabel `VPN_SERVERS` berisi JSON array seperti contoh di `.env.example`. Pilihan server otomatis muncul di form.
