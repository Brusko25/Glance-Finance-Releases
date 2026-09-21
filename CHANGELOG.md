# Changelog

## 2.6.0 — 2026-09-21

- Redesign the control panel as a Glance workspace with top navigation, a copper-and-ink theme, a right-side tile dock, and an Overview dashboard with a clickable desktop map.
- Add show/hide-all tile controls and True black, Ink and Paper presets with a sample preview. Expand asset browsing to six results per page and reorganize portfolio metrics.

- Save the current tile setup and load it later to restore positions, sizes, closed tiles, chart ranges and appearance.

- Reduce chart side margins: price labels sit near the left edge, and the graph extends closer to the right edge.

## 2.5.0 — 2026-09-20

- Snap nearby widget edges together while dragging, with a saved toggle under Update Layout.

- Keep the three horizontal chart gridlines at fixed heights and use round price references with intervals suited to the visible range.

## 2.4.2 — 2026-09-15

- Detect newer stable releases at startup and daily; add manual update checks and optional links to the product download page.

## 2.4.1 — 2026-09-14

- Restored the Glance Finance name for the stock, crypto, and portfolio app. Corrected app branding, installer shortcuts, and repository links. Existing installation folders and workspace files are preserved. Updates remain manual.
- Version 2.4.0 was mistakenly branded Glance LLM Usage; that name belongs to the separate usage widget. Historical release names remain recorded below.

## 2.4.0 — 2026-09-13

- Renamed Glance Finance to Glance LLM Usage across the app, installer, shortcuts, documentation, and GitHub repositories.
- Preserved the existing stock, crypto, portfolio, and chart features and the saved-workspace format. Existing installations retain their original folder during upgrades.
- Refreshed release screenshots with popular stock and crypto examples showing both green gains and red losses.

## 2.3.0 — 2026-09-13

- Centered each chart on its average visible market price, with an equal price range above and below and room for all highs and lows.
- Set Yahoo chart sampling to 5 minutes for 1D, 30 minutes for 1W, and 180 minutes for 1M, including pre-market and after-hours data when supplied. Monthly samples combine 30-minute feed bars while preserving final prices and total volume. Newer extended-session prices update the widget header and are identified in its provider tooltip.

- Added three evenly spaced, rounded price references and horizontal gridlines to every chart. Reference intervals use half the initial spacing for a tighter scale while retaining the full price movement. Label precision follows the price range, and the left margin expands for longer prices.

- Stock, fund and index charts compress time without market samples, removing long overnight and weekend stretches. The 1W view uses the latest five trading sessions with labels centered on their actual dates. Crypto retains five consecutive calendar days. Price, hover and volume positions share the same timeline; the widget layout stays unchanged.
- Widget backgrounds are solid colors without a gradient, with true black (#000000) as the default.

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
