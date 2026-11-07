# Design — Katalog & Dompet

- catalog.py: daftar produk sebagai dataclass Product(id, nama, harga, harga_coret=None, kategori).
- wallet.py: class Wallet(saldo) dengan buy(product, gratis=False) -> Receipt | Error; menahan daftar orders.
- Promo dihitung di wallet: flag promo_terpakai per sesi; engine menanyakannya sebelum CONFIRM kedua.
- Receipt dirender menjadi teks struk oleh menus.py.
