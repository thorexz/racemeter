# RaceMeter V2 — Advanced Motorcycle Edition

## Fitur
- GPS browser real-time dengan `watchPosition`
- Estimasi akurasi lokasi, koordinat, dan status GPS
- Pencatatan perjalanan: durasi, jarak berbasis titik GPS, jumlah titik
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
- Tidak menampilkan tes kecepatan, akselerasi, top speed, atau pengereman.
- Bukan alat navigasi atau alat ukur tersertifikasi.
- Siapkan aplikasi sebelum perjalanan, pasang ponsel dengan aman, jangan berinteraksi dengan layar saat berkendara.
- Data tersimpan lokal. Ekspor backup secara berkala. Belum ada sinkronisasi Apps Script/Sheets pada build ini.
