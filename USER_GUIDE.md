# Glance Finance user guide

Version 2.0.1 · Windows 10/11 · .NET Framework 4.8

## Open and close

Extract the downloaded ZIP to a writable folder, then double-click **GlanceFinance.exe**. This opens the control panel and restores your widgets. Launching it again brings the existing panel forward.

Closing the panel keeps widgets running. Open it again from a widget's menu, Ctrl+M while a widget is focused, or the system tray icon. Use **Quit** to close the entire app. Removing a widget does not affect your portfolio.

## Control panel

- **Home:** search a company or symbol, filter All / Stocks / Funds / Indices / Futures / Forex / Crypto, and use + to add any search result as a desktop widget. The arrows below the results show more matches. Includes live market headlines, daily movers among tracked assets and reference symbols, and a personal calendar.
- **Portfolio:** record buys, sells, and cash dividends for USD stocks, funds, and crypto. See holdings, average cost, market value, unrealized/realized P&L, dividends, and a transaction ledger. Fees are included. Entries stay local; they do not submit brokerage orders. Backdated sales are checked against the entire transaction history. Removing a transaction is prevented if it would leave a later sale without enough units.
- **Update Layout:** resize all widgets, arrange a grid, align edges or stack vertically, snap to a 24-pixel grid, show a mini header, lock positions, enable mouse click-through, and change default width/height. Width and height changes apply to all widgets. Grid and alignment are explicit placement commands even when dragging is locked.
- **Color Settings:** foreground palette and custom colors; separate up/down colors; optional price-change flashes; background palette; 50–100% opacity; and optional volume bars with a custom color. Changes apply immediately to all widgets.
- **Keybindings:** click a shortcut field and press a replacement combination. Duplicate bindings are rejected. These are local shortcuts, active when a widget is focused.
- **My Widgets:** show/hide, bring forward, remove, pin, and change the range of an individual widget. Newly added widgets are placed beside existing ones when space permits.

If click-through is enabled, use the control panel or the tray's **Restore mouse interaction** command to turn it off.

## Widget controls

Drag the header beside the symbol to move. Click the symbol to switch among the six built-in coins, or use Home to add any supported market symbol. Hover over the chart for a historical price. Click **1D / 1W / 1M** for a day, week, or month view. Click **...** or right-click for the control panel, pinning, size, refresh, and close.

Default keyboard shortcuts: **Ctrl+R** refresh, **Ctrl+P** pin, **1 / 2 / 3** chart range, **Ctrl+M** control panel, **Alt+F4** close widget. Mini mode shows the header only; use its context menu, shortcuts, or the panel to manage it.

## Market data and calculations

The six built-in coins use public Coinbase Exchange data. Other symbols use Yahoo Finance's public search/chart endpoints. Requests and responses were verified during development, but Yahoo's public endpoints are unofficial and can change or become unavailable. The app displays unavailable/stale states and retries instead of supplying synthetic prices.

Widgets request quotes every 15 seconds and chart history every five minutes, or immediately after a range change. The panel refreshes prices every minute. Requests run asynchronously; selection changes cancel older widget requests. News is loaded from Yahoo's RSS feed and can be refreshed on Home. Headlines link to their publishers.

Crypto ranges are rolling 1 / 7 / 30 days; other assets use a session / five trading days / month. If the current day has no candles, a one-day chart falls back to the last available session. Charts use sampled candles plus the latest available quote, so gaps or delays from the source can remain visible. Intraday Yahoo points use the source's bucket timestamp; Coinbase points use the bucket close. Times display in the PC's local timezone. A widget's return compares its latest price with the first available candle's opening price in the selected range. Chart currency follows the feed.

The panel's movers compare against the previous daily close (rolling 24-hour opening price for Coinbase crypto). They are ranked within the fetched reference/tracked symbols, not the entire market. Closed markets are shown with their last available trade time. Futures and forex quotes are for display; the portfolio does not calculate futures contract multipliers or currency conversion.

Portfolio totals use USD-denominated positions and average-cost accounting, including fees. Missing or unusable USD quotes leave valuation totals unavailable. The **1D price P&L** is price movement multiplied by the quantity currently held; it does not reconstruct intraday positions. Total P&L includes realized gains, unrealized gains, and cash dividends. This is a personal tracker, not a tax-accounting engine.

Upcoming events is a manual personal calendar, not an automatic earnings/economic feed or notification service. No startup registration, cloud sync, subscription, or paid feature system is installed.

## Saved data

Widgets, layout, colors, shortcuts, calendar entries and transactions are saved beside the executable in **workspace.json**, with the previous save in **workspace.json.bak**. The first version's **settings.json** is imported on the first launch of version 2 and left in place. A damaged workspace is preserved with an `.unreadable-<timestamp>` suffix before a fresh workspace is used. Copy the executable and workspace into a writable folder for a portable copy.


## Downloads, updates and support

Download the Windows ZIP from [Glance Finance Releases](https://github.com/Brusko25/Glance-Finance-Releases/releases/latest).
GitHub's automatic Source code archives contain release documentation, not the app.
Updates are manual: use **Quit**, back up your workspace.json, and extract the
new executable and documentation over the old folder. The ZIP never includes a
workspace or settings file. The current executable is unsigned.

Report problems through [GitHub Issues](https://github.com/Brusko25/Glance-Finance-Releases/issues).
Include the app version (shown under About), Windows version, reproduction steps,
and exception text if present. Remove personal paths and portfolio information.
Do not attach workspace.json, settings, backups or account credentials.
