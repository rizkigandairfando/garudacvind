# BrandMe AI — versi tanpa API

Aplikasi frontend satu file untuk prototipe CV dan personal branding tanpa API AI berbayar.

## Login dan logout
- Buat akun dengan nama, username, dan kata sandi melalui layar **Daftar akun**.
- Login menggunakan username dan kata sandi. Tombol **Keluar** mengakhiri sesi pada browser.
- Data CV, hasil tes, dan dokumen dipisahkan berdasarkan username di browser/perangkat yang sama.
- Akun ini bersifat lokal, bukan autentikasi server. Data tidak tersinkron ke perangkat lain dan tidak cocok untuk aplikasi publik/multi-user online. Kata sandi disimpan sebagai hash bila browser mendukung Web Crypto, tetapi penyimpanan lokal tetap tidak memberikan keamanan setara server.

## Fitur yang berjalan
- Dashboard dan menu navigasi responsif.
- Generator CV berbasis template/aturan (bukan AI generatif).
- Editor CV manual, pilihan template dan warna, preview langsung.
- Simpan CV di `localStorage`.
- Cetak CV/portofolio melalui dialog browser lalu pilih **Save as PDF**.
- Upload dokumen PDF/JPG/PNG sampai 5 MB per file ke IndexedDB lokal.
- Lihat, unduh, hapus dokumen dan pilih metadata yang ditampilkan di preview portofolio.
- Tes kesiapan kerja 8 soal dengan penilaian berbasis kunci/rubrik sederhana.
- Riwayat tes lokal.
- Pengaturan nama dan WhatsApp Click to Chat.
- Ekspor/impor cadangan JSON untuk data profil/CV/hasil tes.
- Tombol Canva membuka Canva.com; tidak ada integrasi API Canva.

## Cara menjalankan
1. Ekstrak ZIP.
2. Buka `index.html` di browser modern, atau jalankan server lokal:
   - Python: `python -m http.server 8000`
   - Buka `http://localhost:8000`
3. Buka Pengaturan, masukkan nama dan nomor WhatsApp admin dalam format internasional, contoh `6281234567890`.
4. Mulai dari Buat CV dengan Template, lalu simpan.

## Penyimpanan dan privasi
- CV, pengaturan, dan hasil tes disimpan pada `localStorage`.
- File dokumen disimpan pada IndexedDB di browser/perangkat ini.
- Data tidak otomatis tersinkron ke perangkat lain dan tidak otomatis tersimpan di cloud.
- Menghapus data situs/browser dapat menghapus data lokal. Ekspor JSON tidak menyertakan file dokumen.
- Tidak ada API AI, backend, akun/login, database online, atau URL portofolio publik.
- Portofolio hanya preview lokal. Untuk berbagi online ke orang lain, aplikasi harus dikembangkan dengan hosting/backend.
- Dokumen disimpan lokal, tetapi keamanan tetap bergantung pada keamanan perangkat/browser. Jangan gunakan perangkat bersama untuk dokumen sensitif.

## Batasan yang disengaja
- "Generate" merangkai data yang dimasukkan pengguna ke template; bukan AI yang memahami atau menulis bebas.
- Tes kesiapan adalah latihan mandiri, bukan asesmen tervalidasi, sertifikasi resmi, atau jaminan diterima kerja.
- Tombol WhatsApp baru berfungsi setelah nomor admin valid disimpan.
- Canva dibuka sebagai situs eksternal. CV tidak dikirim otomatis ke Canva dan AI Canva tidak dikendalikan oleh aplikasi.
- PDF dibuat melalui dialog cetak browser; pada dialog pilih printer "Save as PDF".

## Deployment
Bisa di-host sebagai situs statis di GitHub Pages, Netlify, atau Vercel. Karena seluruh data lokal di browser, deployment tidak memerlukan environment variables. Jangan menyebutnya multi-user/cloud app tanpa backend dan autentikasi.
