# USSD Bangkit — Toko *123#

The dead *123# USSD menu rises again: shop premium apps, game top-ups, and mobile credit
from a retro feature-phone screen — powered by a modern engine and one friendly ghost.

A Kiroween 2026 entry (Resurrection category). Built with Kiro using spec-driven
development — see the `/.kiro` directory for specs, steering docs, and hooks.

## Run locally
```
pip install nicegui pytest hypothesis
python -m app.main
```
Then open the local address NiceGUI prints, dial *123# on the phone keypad, and shop.
Demo wallet: Rp500.000. Demo PIN: 123456 (also shown in the Help menu inside the app).

## Stack
Python everywhere — NiceGUI UI, a pure-Python USSD session state machine,
pytest + hypothesis property-based tests for the navigation invariants.
