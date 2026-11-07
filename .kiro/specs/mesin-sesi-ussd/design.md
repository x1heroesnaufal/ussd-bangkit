# Design — Mesin Sesi USSD

## Mesin status
State: IDLE, MAIN, CATEGORY, PRODUCT, CONFIRM, PIN, DONE, HELP, BALANCE, HISTORY, ENDED.
Objek Session: state, stack layar (untuk # = pulang ke MAIN), saldo_snapshot, keranjang produk terpilih,
jumlah_salah_pin, jumlah_salah_input, last_activity (untuk timeout 90 detik).

## Antarmuka modul
- engine.new_session() -> Session
- engine.handle_input(session, text) -> Screen(text: str, ended: bool)
- engine.tick(session, now) -> Screen | None  (memeriksa timeout)
Mesin tidak mengimpor NiceGUI sama sekali; UI hanya menerjemahkan klik keypad menjadi handle_input.

## Korektness properties (untuk property-based test)
- P1: Dari state apa pun, urutan input valid tidak pernah membuat handle_input melempar error.
- P2: Input "0" pada MAIN selalu mengakhiri sesi (ended=True).
- P3: Saldo dompet tidak pernah negatif setelah urutan pembelian apa pun.
- P4: Setelah ENDED, sesi baru selalu bisa dimulai dengan *123#.

## Layar
Setiap layar maksimal 9 baris, diakhiri "Balas dengan nomor:" kecuali DONE/ENDED.
Teks layar didefinisikan di menus.py agar mudah diubah tanpa menyentuh engine.
