# Changelog

## 2.0.1 — 2026-09-07

First GitHub distribution of Glance Finance.

### Added

- Dark Windows control panel with Home, Portfolio, Update Layout, Color Settings,
  Keybindings and individual widget controls.
- Multiple floating widgets, market search, stock/fund/index/futures/forex/crypto
  categories, sampled charts, hover prices and quote freshness labels.
- Local USD transaction ledger with average cost, fees, realized and unrealized
  P&L, dividends, and checks against backdated overselling.
- Grid placement, alignment, mini mode, position locking, click-through, opacity,
  color palettes, volume bars and configurable widget shortcuts.
- News headlines, manual calendar dates, persistent settings and tray controls.
- Windows CI, isolated regression tests, private source/public download separation,
  versioned portable packages and SHA-256 checksums.

### Fixed

- A disposed-font exception during button repainting and resizing. Widget-owned
  fonts now remain alive until their controls close; disposal is idempotent.
- Quote retrieval for feeds that return a valid price without current-session
  candles; one-day charts fall back to the last available session when possible.

### Limitations

- Yahoo's public endpoints are unofficial and can change or become unavailable.
- Prices may be delayed or show a closed market's last trade.
- Portfolio valuation supports USD assets; no brokerage orders or currency
  conversion are performed. Calendar dates are entered manually.
- Windows binaries are unsigned. Updates are installed manually.
