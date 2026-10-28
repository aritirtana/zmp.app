# ZMP App – Faktur & Akuntansi (Android)

Project Capacitor siap build. Isi aplikasi ada di `www/` (index.html, mobile.css, native.js).
Login awal: **admin / admin123** (segera ganti di menu "Ganti password").

## Cara 1 – Build otomatis di GitHub (tanpa install apa pun di PC)
1. Buat repository baru di github.com, upload seluruh isi folder ini (termasuk folder `.github` dan `android`).
2. Buka tab **Actions → Build APK → Run workflow** (atau otomatis saat push).
3. Setelah hijau (±5 menit), buka run tersebut → **Artifacts → ZMP-App-apk** → unduh, ekstrak, pindahkan `app-debug.apk` ke HP dan install (izinkan "Install dari sumber tidak dikenal").

## Cara 2 – Build di PC (Android Studio)
1. Pasang Node 22, Android Studio (JDK 21 + SDK 36).
2. `npm install` lalu `npx cap sync android`
3. `npx cap open android` → Build → Build APK(s).
   Atau terminal: `cd android && ./gradlew assembleDebug`
   Hasil: `android/app/build/outputs/apk/debug/app-debug.apk`

## Setelah mengubah HTML
Edit `www/index.html`, lalu jalankan `npx cap sync android` dan build ulang.

## Catatan
- Data tersimpan di penyimpanan aplikasi (offline). Menghapus data/uninstall aplikasi menghapus data → rutin pakai **Pengaturan → Unduh cadangan**.
- Cetak faktur/laporan memakai dialog cetak Android (pilih "Simpan sebagai PDF").
- Untuk Play Store perlu AAB release bertanda tangan (`./gradlew bundleRelease` + keystore).
