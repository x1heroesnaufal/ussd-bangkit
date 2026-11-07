# Tasks — Mesin Sesi USSD

- [ ] 1. Buat app/ussd/engine.py: Session + handle_input untuk IDLE dan MAIN (dial *123#, menu utama, input tidak valid).
- [ ] 2. Tambahkan navigasi CATEGORY dan PRODUCT memakai katalog dari spec katalog-dompet.
- [ ] 3. Tambahkan CONFIRM dan PIN (bintang, 3x salah batal) yang memanggil wallet.buy().
- [ ] 4. Tambahkan BALANCE, HISTORY, HELP, dan aturan 0 keluar + # pulang.
- [ ] 5. Tambahkan timeout 90 detik lewat tick().
- [ ] 6. Tulis tests/test_engine.py (pytest) untuk semua acceptance criteria.
- [ ] 7. Tulis tests/test_properties.py (hypothesis) untuk P1–P4.
- [ ] 8. Hubungkan keypad NiceGUI di app/main.py ke engine (klik + keyboard).
