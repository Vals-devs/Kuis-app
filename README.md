# 🧠 QuizBattle — Kuis Interaktif Real-Time

Aplikasi kuis interaktif seperti Kahoot untuk pembelajaran algoritma sorting. Mendukung hingga 50 peserta secara real-time!

## ✨ Fitur

- 🎯 **Host**: Buat sesi kuis, kontrol jalannya kuis, lihat statistik jawaban real-time
- 🎮 **Peserta**: Join dengan kode, jawab soal, lihat ranking real-time
- 🎵 **Musik & Efek Suara**: Musik lobby, countdown, efek benar/salah, fanfare kemenangan
- ⏱️ **Timer 20 detik** per soal dengan musik countdown yang semakin intens
- 📊 **Leaderboard** setelah setiap soal dan di akhir kuis
- 🎉 **Skor berbasis kecepatan** — semakin cepat menjawab, semakin tinggi poin
- 📱 **Responsif** — bisa diakses dari HP maupun laptop
- 🎨 **Desain menarik** dengan animasi dan warna-warna cerah

## 🔧 Cara Setup Firebase

### Langkah 1: Buat Project Firebase

1. Buka [console.firebase.google.com](https://console.firebase.google.com)
2. Klik **"Add project"** / **"Tambahkan project"**
3. Beri nama project (contoh: `quiz-battle-app`)
4. Google Analytics boleh dimatikan (tidak diperlukan)
5. Klik **"Create project"**

### Langkah 2: Aktifkan Realtime Database

1. Di sidebar kiri, klik **"Build"** → **"Realtime Database"**
2. Klik **"Create Database"**
3. Pilih lokasi terdekat (contoh: `asia-southeast1` untuk Indonesia)
4. Pilih **"Start in test mode"** → Klik **"Enable"**

### Langkah 3: Set Database Rules

1. Di halaman Realtime Database, klik tab **"Rules"**
2. Ganti isinya dengan:

```json
{
  "rules": {
    "sessions": {
      ".read": true,
      ".write": true
    }
  }
}
```

3. Klik **"Publish"**

> ⚠️ **Catatan**: Rules di atas bersifat terbuka untuk kemudahan. Untuk keamanan lebih, Anda bisa membatasi write rules sesuai kebutuhan.

### Langkah 4: Dapatkan Konfigurasi Firebase

1. Di sidebar kiri, klik ikon ⚙️ (gear) → **"Project settings"**
2. Scroll ke bawah ke bagian **"Your apps"**
3. Klik ikon **"</>"** (Web) untuk menambahkan aplikasi web
4. Beri nama (contoh: `quiz-battle`) → Klik **"Register app"**
5. Salin objek `firebaseConfig` yang muncul

Contoh konfigurasi:
```javascript
const firebaseConfig = {
    apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXX",
    authDomain: "quiz-battle-app.firebaseapp.com",
    databaseURL: "https://quiz-battle-app-default-rtdb.asia-southeast1.firebasedatabase.app",
    projectId: "quiz-battle-app",
    storageBucket: "quiz-battle-app.appspot.com",
    messagingSenderId: "123456789",
    appId: "1:123456789:web:abcdef123456"
};
```

### Langkah 5: Masukkan Konfigurasi ke Aplikasi

1. Buka file `index.html` dengan text editor
2. Cari bagian `firebaseConfig` di bagian atas `<script>`
3. Ganti semua value `"GANTI_DENGAN_..."` dengan value dari Firebase:

```javascript
const firebaseConfig = {
    apiKey: "PASTE_API_KEY_DISINI",
    authDomain: "PASTE_AUTH_DOMAIN_DISINI",
    databaseURL: "PASTE_DATABASE_URL_DISINI",
    projectId: "PASTE_PROJECT_ID_DISINI",
    storageBucket: "PASTE_STORAGE_BUCKET_DISINI",
    messagingSenderId: "PASTE_SENDER_ID_DISINI",
    appId: "PASTE_APP_ID_DISINI"
};
```

4. Simpan file

## 🚀 Cara Menjalankan

### Cara Paling Mudah
1. Double-click file `index.html` untuk membukanya di browser
2. Selesai! Aplikasi siap digunakan.

### Menggunakan Live Server (Recommended)
Jika Anda menggunakan VS Code:
1. Install extension **"Live Server"**
2. Klik kanan `index.html` → **"Open with Live Server"**
3. Aplikasi akan terbuka di browser dengan URL `http://127.0.0.1:5500`

> **💡 Tips**: Menggunakan Live Server lebih baik karena URL-nya bisa dibagikan ke perangkat lain di jaringan yang sama.

## 📖 Cara Penggunaan

### Untuk Host (di laptop/PC yang diproyeksikan):

1. Buka aplikasi di browser
2. Klik **"🎯 Buat Kuis"**
3. Bagikan **kode sesi** (6 karakter) ke peserta
4. Tunggu peserta masuk (terlihat di daftar peserta)
5. Klik **"▶ Mulai Kuis"** ketika semua peserta sudah ready
6. Soal akan muncul dengan timer 20 detik
7. Setelah waktu habis, klik **"🏆 Lihat Leaderboard"**
8. Klik **"➡️ Soal Berikutnya"** untuk lanjut
9. Setelah 10 soal, lihat **Hasil Akhir** dengan podium 🎉

### Untuk Peserta (di HP masing-masing):

1. Buka aplikasi di browser HP
2. Klik **"🎮 Gabung Kuis"**
3. Masukkan **kode sesi** dari host
4. Masukkan **nama/nickname**
5. Klik **"🚀 Gabung!"**
6. Tunggu host memulai kuis
7. Pilih jawaban dengan menekan tombol warna (🔴🔵🟡🟢)
8. Lihat feedback dan ranking setelah setiap soal
9. Lihat peringkat akhir di akhir kuis!

## 🎵 Tentang Musik & Efek Suara

Aplikasi ini menggunakan **Web Audio API** untuk menghasilkan musik dan efek suara langsung di browser tanpa file audio eksternal:

- 🎶 **Musik Lobby**: Melodi fun saat menunggu peserta
- ⏱️ **Musik Countdown**: Detik-detik tegang selama menjawab soal (semakin intens di 5 detik terakhir!)
- ✅ **Efek Benar**: Jingle riang saat jawaban benar
- ❌ **Efek Salah**: Suara sedih saat jawaban salah
- 🥁 **Drum Roll**: Saat menampilkan leaderboard
- 🎺 **Fanfare**: Musik kemenangan di akhir kuis

Klik tombol 🔊 di pojok kanan atas untuk mute/unmute.

## 📋 Spesifikasi Teknis

- **Frontend**: HTML + CSS + JavaScript (single file)
- **Backend**: Firebase Realtime Database (free tier)
- **Audio**: Web Audio API (synthesized, tanpa file eksternal)
- **Max Peserta**: 50 per sesi
- **Jumlah Soal**: 10 soal tentang algoritma sorting
- **Timer**: 20 detik per soal
- **Scoring**: Maks 1000 poin per soal, min 100 poin (berdasarkan kecepatan)
- **Browser**: Chrome, Firefox, Edge, Safari (versi terbaru)

## ❓ Troubleshooting

| Masalah | Solusi |
|---------|--------|
| Muncul "Setup Firebase Diperlukan" | Pastikan `firebaseConfig` sudah diisi dengan benar |
| Kode sesi tidak bisa dimasukkan | Periksa koneksi internet dan status Firebase |
| Musik tidak berbunyi | Klik area manapun dulu (browser butuh interaksi user), cek tombol mute |
| Peserta tidak muncul di daftar host | Pastikan host dan peserta menggunakan Firebase yang sama |
| Timer tidak sinkron | Pastikan waktu perangkat sudah benar, Firebase otomatis mengoreksi offset |

## 📄 Lisensi

Free to use for educational purposes. Dibuat untuk pembelajaran yang menyenangkan! 🎓
