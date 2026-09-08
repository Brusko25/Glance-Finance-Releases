# Changelog

## 2.2.0 — 2026-09-08

- Fixed Home category-tab flashing by updating only the active tab and reusing result rows, preserving search state and the rest of the page.

## 2.1.0 — 2026-09-08

- Added a custom chart icon to the app, tray, installer and shortcuts.
- Clean chart tiles with plain symbol text, no bottom controls, and time ranges in the right-click menu.
- Bold tile names and 14-pixel prices and a thicker arrow with longer tip wings.
- Percentage, arrow and chart color now reflect the first visible plotted price through the latest price.
- Fixed toggle background repaint artifacts and refined keyboard-focus outlines.
- Added the top 100 coins by market cap (CoinGecko snapshot, September 8, 2026), with name/symbol search and grouped coin menus. Added cached CoinGecko quote/history support for the expanded catalog.
- Added saved per-widget locking and native corner resizing with stable text sizes.
- Added a per-user Windows installer with Start menu entry, optional desktop shortcut, and an uninstaller that preserves saved workspaces. Portable ZIP remains available.

Public feeds may be delayed or rate-limited. Rankings are a release snapshot. Both installer and application are unsigned.

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
