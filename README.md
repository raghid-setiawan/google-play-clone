![Edukasi Only](https://img.shields.io/badge/Edukasi%20Only-Important-red?style=flat-square&logo=bookstack)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-yellow?style=flat-square&logo=javascript)
![Telegram Bot](https://img.shields.io/badge/Telegram%20Bot-Integrated-blue?style=flat-square&logo=telegram)
![License](https://img.shields.io/badge/License-CC0--1.0-lightgrey?style=flat-square)

# 🚀 Google Play Clone – Telegram Bot & JS Obfuscation

## ⚠️ **Peringatan Etika & Hukum** (Wajib Baca!)
**Project ini 100% hanya untuk tujuan edukasi, dokumentasi, dan riset keamanan pribadi.**

- Notifikasi Telegram hanya boleh dikirim ke akun/Chat ID milik sendiri.
- Dilarang keras memantau, mengumpulkan data, atau mengirim info ke orang lain tanpa izin eksplisit → melanggar UU ITE, UU PDP, dll.
- Penulis tidak bertanggung jawab atas segala bentuk penyalahgunaan kode ini.

---

## 📖 **Daftar Isi**
1. Pengenalan  
2. Fitur Utama  
3. Instalasi & Setup  
4. Build Project  
5. Struktur Folder  
6. Alur Kerja (Educational)  
7. Catatan Keamanan  
8. Legal Notice  

---

## 🎯 **Pengenalan**  
Clone sederhana tampilan Google Play Store (support PWA) yang terintegrasi dengan Telegram Bot untuk kirim notifikasi event, plus JavaScript Obfuscation untuk proteksi kode.

Tujuan utama:  
- Belajar integrasi Telegram Bot API ke website  
- Memahami teknik obfuscation JS agar kode susah dibaca/dimodifikasi  
- Mengamati event flow di environment lokal pribadi

---

## ✨ **Fitur Utama**  
- UI mimic Google Play Store (index.html + manifest.json + sw.js)  
- Telegram Bot kirim notifikasi real-time (page open, touch event, klik download)  
- Obfuscation JS otomatis via npm run build  
- Output di folder dist/  
- Ambil User-Agent untuk edukasi fingerprinting dasar

---

## 🧰 **Instalasi & Setup**

1. Clone repo:  
   git clone https://github.com/raghid-setiawan/google-play-clone.git  
   cd google-play-clone

2. **Ganti placeholder wajib (EDUKASI ONLY - lakukan untuk test lokal SAJA)**  
   - **index.html**  
     Cari teks **Huggle: Free Video Call** → ganti jadi nama APK kamu sendiri (misal: "My Test App v1.0")  

   - **js/app.js**  
     - Ubah pesan notif: `await sendTelegram('User started APK download');` → bisa diganti lebih spesifik (contoh: `'Download dimulai: nama-apk.apk'`)  
     - Ubah link download: `link.href = 'https://t.me/Sec_Society';` → ganti jadi `'apk/nama-file-kamu.apk'` (direct dari folder apk/) atau link eksternal lain  
     - Ubah nama file download: `link.download = 'test.apk';` → ganti jadi nama file APK asli (misal: `'my-app-v1.apk'`)  

   - **Setup Telegram Bot**  
     Buka file **js/app.js**  
     Cari baris:  
     `const TG_TOKEN = '';//YOUR BOT TOKEN`  
     `const TG_CHAT = '';//YOUR CHAT ID`  
     Ganti nilai di dalam '' dengan token & chat ID milikmu sendiri **untuk test lokal SAJA**  
     Setelah test selesai, **kembalikan ke ''** sebelum commit/push!

3. Install dependencies:  
   npm install

**Catatan penting:**  
- Semua penggantian di langkah 2 hanya untuk eksperimen pribadi  
- **Jangan commit** token, link, atau nama file asli ke repo  
- Kembalikan semua placeholder ke nilai awal sebelum push
  
---

## 🛠 **Build Project**
Jalankan perintah berikut untuk membangun versi obfuscated:  
npm run build  

Proses build akan menghasilkan folder dist/ yang berisi file-file sudah diobfuscate.  
Contoh output terminal yang sukses:  
Build complete. See dist/ for obfuscated output.  

Screenshot proses build, struktur folder, kode konfigurasi Telegram, dan preview halaman di browser:  

![Screenshot Build Process & Project Overview](https://i.imgur.com/Mm3BXzT.jpeg)
*(Gambar menampilkan VS Code dengan app.js, terminal npm run build sukses, struktur folder, dan preview Google Play clone di browser)*

Test lokal setelah build:  
npx live-server dist/  
Buka http://localhost:8080 → lakukan interaksi → cek notifikasi masuk di Telegram pribadimu.

---

## 📁 **Struktur Folder**  
.  
├── apk/                 # Contoh APK (edukasi only)  
├── dist/                # Hasil build obfuscated  
├── img/                 # Asset gambar (termasuk screenshot & blueprint)  
├── js/                  # Source JS (app.js dll)  
├── scripts/             # Build script (build.js)  
├── index.html  
├── manifest.json  
├── sw.js  
├── package.json  
├── package-lock.json  

---

## 🔎 **Alur Kerja (Educational)**  
1. Buka halaman localhost  
2. Event listener aktif (DOMContentLoaded, touch, dll)  
3. Kumpul info sederhana (User-Agent, event)  
4. Kirim via fetch ke Telegram API (bot milik sendiri)  
5. Bot terima notifikasi  
6. Kode di dist/ sudah obfuscated → latihan proteksi source

---

## 🔐 **Catatan Keamanan & Edukasi**  
- JANGAN commit token/chat ID asli ke repo  
- Gunakan bot token khusus testing (bikin baru via @BotFather)  
- Test hanya di localhost / VM / sandbox pribadi  
- Obfuscation untuk belajar proteksi kode, bukan untuk hal negatif  
- Ide lanjutan (legal): deteksi DevTools, anti-debug check

---

## 📜 **Legal Notice**  
- Project ini murni untuk edukasi dan penelitian pribadi  
- Gunakan secara legal dan etis  
- Ide awal dari sumber edukasi Telegram, hanya untuk pembelajaran
