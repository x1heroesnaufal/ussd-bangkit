# Struktur Folder

- app/main.py — titik masuk NiceGUI, merakit halaman (HP + panel MODERN).
- app/ussd/engine.py — mesin sesi USSD (mesin status murni, tanpa UI).
- app/ussd/menus.py — definisi pohon menu dan teks layar.
- app/store/catalog.py — katalog produk demo.
- app/store/wallet.py — dompet demo, saldo, riwayat pesanan.
- app/dashboard/panel.py — panel MODERN (umpan pesanan, total, papan kurs).
- tests/ — pytest + hypothesis.
- .kiro/ — spec, steering, hooks. Folder ini WAJIB ikut ter-commit (jangan masuk .gitignore).
