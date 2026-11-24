# Membuat APK Ujian Terjaga (otomatis, tanpa Android Studio)

Repo ini membuat DUA APK sekaligus: Siswa dan Guru. APK-nya sudah bertanda tangan
(tanda tangan debug), jadi tidak muncul error "paket tidak valid" seperti APK unsigned.
Semua berjalan di server GitHub, kamu tidak perlu memasang apa pun di komputer.

## Langkah
1. Buat akun di github.com (gratis), lalu buat repository baru (misalnya `ujian-terjaga`), Private juga boleh.
2. Di halaman repo kosong, klik "uploading an existing file", lalu seret SEMUA isi folder ini
   (termasuk folder `.github`, `www-guru`, `www-siswa`, dan `package.json`). Klik Commit changes.
   - Kalau folder `.github` tidak ikut terunggah: klik Add file > Create new file,
     ketik nama `.github/workflows/apk.yml`, lalu tempel isi file apk.yml.
3. Buka tab **Actions**. Proses "Bangun APK" jalan otomatis (sekitar 5 sampai 10 menit).
   Kalau tidak jalan, klik "Bangun APK" lalu "Run workflow".
4. Setelah centang hijau, klik proses itu, gulir ke bawah ke bagian **Artifacts**,
   unduh `APK-siswa` dan `APK-guru`. Masing-masing berupa zip: ekstrak, di dalamnya `app-debug.apk`.
5. Kirim APK ke HP dan pasang. Izinkan "pasang dari sumber tidak dikenal" kalau diminta.

## Memperbarui aplikasi
Ganti `www-siswa/index.html` atau `www-guru/index.html` dengan versi baru, commit, lalu ambil APK baru
dari Actions. Pasang di atas yang lama (paket dan tanda tangan debug kunci yang sama di mesin yang
sama tidak dijamin, jadi kalau gagal menimpa, hapus aplikasi lama dulu).

## iPhone
APK tidak bisa dipasang di iPhone. Untuk iOS pakai paket aplikasi terpasang (PWA) dari zip sebelumnya:
Safari, Bagikan, Tambah ke Layar Utama.
