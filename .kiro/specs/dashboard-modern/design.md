# Design — Panel MODERN

- panel.py memakai elemen NiceGUI dengan timer 1 detik untuk umpan dan 30 detik untuk kurs.
- Sumber kurs: satu fungsi fetch_rates() yang mudah diganti; fallback simulasi deterministik per jam.
- Animasi hantu: elemen gambar SVG sederhana yang digerakkan dengan CSS transition saat event pesanan.
