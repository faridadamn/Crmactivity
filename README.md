# CRM Activity

Single-file HTML CRM app for sales activity, prospects, pipeline, and follow-up.

## Cara menjalankan
Buka `crm-activity.html` langsung di browser. Data demo dan perubahan pengguna disimpan di browser menggunakan `localStorage`.

## Roadmap
1. Fondasi aktivitas dan prioritas harian
2. Profil prospek dan pipeline
3. Follow-up dan anti-lupa
4. Target, KPI, dan gamifikasi
5. Laporan manajerial
6. AI CRM assistant

## Iteration Log

### Iterasi 1 — Fondasi Aktivitas dan Prioritas
- **Tujuan:** Menjadikan aplikasi sebagai alat kerja harian yang cepat untuk merencanakan, menjalankan, dan menutup aktivitas sales.
- **Perubahan:** Dashboard prioritas hari ini, KPI visit/deal/pipeline, status dan tipe aktivitas, form tambah/ubah aktivitas, tandai selesai, jadwal ulang, dan target harian.
- **Hasil:** Baseline `crm-activity.html` fungsional penuh, tersimpan di `localStorage`.

### Rebuild — Revert ke Baseline dan Implementasi Ulang Iterasi 2-4
- **Konteks:** Iterasi 2-4 sebelumnya sempat dipush sebagai versi statis/mockup tanpa JavaScript (tombol dan data tidak berfungsi) karena iterasi oleh agent lain gagal mempertahankan interaktivitas. Riwayat commit dikembalikan ke baseline awal (`Add files via upload`) dan seluruh fitur berikut dibangun ulang secara dinamis dalam satu file agar benar-benar berfungsi, bukan sekadar tampilan.
- **Iterasi 2 — Profil Prospek dan Pipeline:** Profil prospek lengkap (PIC, no. WhatsApp, lokasi, kategori bisnis, nilai potensi, produk diminati, catatan kebutuhan, risiko/alasan lost), papan pipeline visual 8 tahap (Prospek Baru, Qualified, Meeting, Proposal, Negosiasi, Deal, Lost, Repeat Order) dengan tampilan papan dan daftar, serta histori aktivitas per prospek.
- **Iterasi 3 — Follow-up dan Anti Lupa:** Dashboard follow-up dengan KPI follow-up hari ini, overdue, customer dingin (>14 hari tanpa kontak), dan peluang hot; tombol WhatsApp cepat dengan template pesan follow-up yang mengirim ke nomor PIC; aturan heuristik next action berdasarkan tahap pipeline, nilai potensi, dan jeda kontak.
- **Iterasi 4 — Target, KPI, dan Gamifikasi:** Target bulanan (visit, follow-up, proposal, deal, omzet) dengan progress bar dinamis, sistem poin otomatis saat aktivitas ditandai selesai (visit +20, follow-up +10, proposal +50, deal +250, repeat order +150), level sales, streak harian, kalender produktivitas 7 hari, badge pencapaian yang terbuka otomatis, dan leaderboard personal.
- **Pengujian:** Validasi sintaks JavaScript, verifikasi seluruh `id` yang direferensikan skrip tersedia di HTML, dan verifikasi seluruh fungsi yang dipanggil dari `onclick`/`onchange` terdefinisi.
- **Hasil:** `crm-activity.html` kini satu file HTML mobile-first yang sepenuhnya interaktif untuk iterasi 1-4, dengan data tersimpan di `localStorage`.
- **Langkah berikutnya:** Iterasi 5 menambahkan laporan manajerial, dashboard tim/multi-sales, filter periode/area/sales/tahap, forecast omzet pipeline, dan ekspor ringkasan.
