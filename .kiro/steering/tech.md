# Teknologi

- Bahasa: Python 3.12 untuk SEMUA hal — logika, mesin sesi, UI, dashboard. Tanpa framework JavaScript.
- UI: NiceGUI (UI ditulis dari Python; update real-time untuk dashboard memakai binding NiceGUI).
- Test: pytest + hypothesis (property-based testing untuk mesin sesi).
- Struktur paket: app/ (kode), tests/ (test). Jalankan aplikasi: `python -m app.main`.
- Gaya kode (wajib): terasa ditulis manusia — komentar singkat seperlunya dalam Bahasa Indonesia,
  penamaan variabel natural, fungsi kecil dan jelas, hindari abstraksi berlebihan dan pola "AI generik".
- Jangan menambahkan dependensi baru tanpa alasan tertulis di spec.
