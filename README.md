# RaceMeter V3 — Advanced Motorcycle Edition

## Fitur
- GPS browser real-time dengan `watchPosition`
- Estimasi akurasi lokasi, koordinat, dan status GPS
- Pencatatan perjalanan: durasi, jarak berbasis titik GPS, jumlah titik
- Auto Stop untuk pencatatan perjalanan biasa dengan pilihan batas 1, 2, 5, 10, atau 20 km; trip disimpan otomatis saat batas tercapai
- Indikator progres menuju batas Auto Stop
- Penyaringan titik GPS: akurasi maksimum 50 m untuk menambah titik; jarak minimum 5 m; lonjakan tidak wajar ditolak
- Profil motor, riwayat servis, catatan BBM
- IndexedDB lokal
- Ekspor dan impor backup JSON
- PWA manifest, ikon, dan service worker untuk cache app shell

## Hosting
Upload keenam file plus `icon.svg` (total 7 file) ke root repository/hosting HTTPS. Service Worker dan geolocation memerlukan HTTPS (localhost untuk development). Aktifkan Pages dari root branch utama jika memakai GitHub Pages.

## iPhone
Buka URL di Safari → Share → Add to Home Screen. Izinkan Location saat diminta. Untuk uji GPS, lakukan saat berhenti di area terbuka. iOS dapat menangguhkan tab/PWA di latar belakang; jangan menganggap pencatatan GPS akan terus berjalan jika layar terkunci atau aplikasi ditutup.

## Batasan akurasi dan keselamatan
- `coords.accuracy` adalah estimasi radius akurasi browser, bukan jaminan ketelitian.
- Jarak dihitung dari koordinat yang lolos filter; hasil dapat kurang/lebih dari jarak sebenarnya karena drift, jeda pembaruan, kondisi langit, dan karakteristik GPS.
- Tidak menampilkan tes kecepatan, akselerasi, top speed, atau pengereman. Auto Stop hanya untuk menyelesaikan log perjalanan biasa berdasarkan jarak total.
- Bukan alat navigasi atau alat ukur tersertifikasi.
- Siapkan aplikasi sebelum perjalanan, pasang ponsel dengan aman, jangan berinteraksi dengan layar saat berkendara.
- Data tersimpan lokal. Ekspor backup secara berkala. Belum ada sinkronisasi Apps Script/Sheets pada build ini.


## RaceMeter V4 — fitur tambahan
- Ringkasan total jarak, total durasi, jumlah trip, dan rata-rata jarak per trip.
- Kategori perjalanan: harian, sekolah, kerja, wisata, dan lainnya.
- Auto Stop untuk pencatatan perjalanan berdasarkan target jarak (500 m hingga 20 km).
- Pengingat servis berdasarkan interval odometer yang dimasukkan pengguna.
- Estimasi konsumsi BBM dari dua pengisian berurutan dan selisih odometer; hasil hanya perkiraan.
- Backup dan restore JSON tetap tersedia.

Catatan: aplikasi menggunakan GPS browser, sehingga jarak dan waktu dapat memiliki selisih. GPS iPhone dapat dihentikan atau ditangguhkan saat aplikasi berada di latar belakang. Siapkan aplikasi saat kendaraan berhenti dan jangan mengoperasikan ponsel saat berkendara. Fitur ini untuk pencatatan perjalanan biasa, bukan pengujian performa kendaraan.


Pembaruan: penanda jarak perjalanan 201 m dan 402 m tersedia sebagai checkpoint notifikasi. Penanda tidak mengukur waktu akselerasi dan tidak menghentikan perjalanan; pencatatan tetap berjalan.
