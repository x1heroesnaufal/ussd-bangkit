# Requirements — Mesin Sesi USSD

## Pendahuluan
Mesin status murni (tanpa UI) yang menjalankan sesi USSD: menerima input digit dari keypad,
mengembalikan teks layar berikutnya. Meniru perilaku USSD asli: sesi dimulai dengan dial,
berakhir dengan keluar/timeout, dan tidak pernah macet.

## Requirements

### Requirement 1: Memulai sesi
**User story:** Sebagai pengunjung, saya menekan *123# supaya sesi toko dimulai.
Acceptance criteria:
1. WHEN pengguna memasukkan "*123#" THEN mesin membuka sesi baru dan menampilkan menu utama.
2. WHEN pengguna memasukkan kode selain *123# THEN mesin menampilkan "Kode tidak dikenal." dan tetap di layar awal.

### Requirement 2: Navigasi menu utama
**User story:** Sebagai pembeli, saya memilih kategori dengan satu digit.
Acceptance criteria:
1. Menu utama menampilkan: 1 Aplikasi Premium, 2 Top-Up Game, 3 Pulsa/Data, 4 Cek Saldo, 5 Riwayat, 9 Bantuan, 0 Keluar.
2. WHEN digit valid dipilih THEN mesin pindah ke layar tujuan.
3. WHEN digit tidak valid dimasukkan THEN mesin menampilkan "Pilihan tidak ada. Coba lagi." dan tetap di menu yang sama; setelah 3x salah berturut-turut sesi diakhiri dengan sopan.

### Requirement 3: Keluar dari mana pun
**User story:** Sebagai pengguna, saya bisa keluar kapan saja.
Acceptance criteria:
1. WHEN pengguna menekan 0 di menu utama atau layar Bantuan THEN sesi berakhir dan layar menampilkan "Sesi berakhir. Terima kasih!" lalu kembali ke layar awal (siap dial lagi).
2. Tombol # di layar mana pun menampilkan kembali menu utama (pulang), kecuali saat memasukkan PIN.

### Requirement 4: Timeout sesi
**User story:** Sebagai sistem, sesi yang diam terlalu lama harus berakhir seperti USSD asli.
Acceptance criteria:
1. IF tidak ada input selama 90 detik THEN sesi berakhir dan layar menampilkan "Sesi berakhir karena waktu habis."

### Requirement 5: Alur beli dan PIN
**User story:** Sebagai pembeli, saya menyelesaikan pembelian dengan konfirmasi dan PIN.
Acceptance criteria:
1. Setelah memilih produk, mesin menampilkan layar konfirmasi berisi nama produk dan harga; 1 = Ya, 0 = Batal.
2. WHEN dikonfirmasi THEN mesin meminta PIN 6 digit; input PIN ditampilkan sebagai bintang.
3. WHEN PIN benar (demo: 123456) THEN pembelian diteruskan ke dompet untuk dieksekusi.
4. WHEN PIN salah 3x THEN pembelian dibatalkan dan sesi kembali ke menu utama.
5. Saldo tidak mencukupi: pembelian ditolak dengan pesan jelas, tanpa mengurangi saldo.
