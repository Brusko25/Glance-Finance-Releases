# Glance Finance user guide

Version 2.6.2 · Windows 10/11 · .NET Framework 4.8

## Open and close

Run the latest **Glance Finance Setup.exe** to install for your Windows user. No administrator rights are required. Setup creates a Start menu entry and offers an optional desktop shortcut. Alternatively, extract the portable Windows ZIP to a writable folder and double-click **GlanceFinance.exe**. Launching it again brings the existing control panel forward.

Closing the panel keeps widgets running. Open it again from a widget's menu, Ctrl+M while a widget is focused, or the system tray icon. Use **Quit** to close the entire app. Removing a widget does not affect your portfolio.

## Glance workspace

Every tab adapts to the available window space. Wider windows use columns for related controls; taller windows show more dashboard content and search results. Resize or maximize the window without losing your active search or entered settings.

- **Overview:** desktop map with clickable tiles, last available quotes for your assets, market headlines and upcoming calendar events.
- **Discover:** search a company or symbol, filter All / Stocks / Funds / Indices / Futures / Forex / Crypto, and use + to add any search result as a desktop widget. The arrows below the results show more matches. Shows more results as the window grows, daily movers among tracked assets and reference symbols, and your calendar.
- **Portfolio:** resize or maximize the window to expand the holdings and transactions tables. Compact rows show more entries; wide windows place all six summary metrics in a single row. Record buys, sells, and cash dividends for USD stocks, funds, and crypto. See holdings, average cost, market value, unrealized/realized P&L, dividends, and a transaction ledger. Fees are included. Entries stay local; they do not submit brokerage orders. Backdated sales are checked against the entire transaction history. Removing a transaction is prevented if it would leave a later sale without enough units.
- **Desktop:** save the current setup and load it later to restore your tiles, resize all widgets, arrange a grid, align edges or stack vertically, snap to nearby tile edges while dragging (enabled by default), snap to a 24-pixel grid, show a mini header, lock positions, enable mouse click-through, and change default width/height. Width and height changes apply to all widgets. Grid and alignment are explicit placement commands even when dragging is locked.
- **Appearance:** True black, Ink and Paper presets with a labeled sample preview; foreground palette and custom colors; separate up/down colors; optional price-change flashes; background palette; 50–100% opacity; and optional volume bars with a custom color. Changes apply immediately to all widgets.
- **Shortcuts:** click a shortcut field and press a replacement combination. Duplicate bindings are rejected. These are local shortcuts, active when a widget is focused.
- **Your tiles:** show/hide, bring forward, remove, pin, and change the range of an individual widget. Newly added widgets are placed beside existing ones when space permits.

If click-through is enabled, use the control panel or the tray's **Restore mouse interaction** command to turn it off.

The right-side **Your tiles** dock stays available on every page. Select a tile to open its controls. **Hide all** temporarily hides your tiles without removing them; **Show all** brings them back. The Overview map reflects your saved tile locations, including hidden tiles with a dashed outline.

## Widget controls

The symbol and price are plain text, and the tile has no bottom buttons. Right-click anywhere for **Time range → 1D / 1W / 1M**, coin selection, control panel, pinning, size, refresh, and close. Hover over the chart for historical prices; provider and freshness details are in the widget tooltip.

Choose **Lock widget in place** to prevent movement and resizing, or **Unlock widget** to edit its placement. Each widget saves its lock. **Desktop → Lock all widgets** overrides these individual settings. When unlocked, drag the top header to move or any corner to resize. With **Snap to other tiles** enabled under **Desktop**, nearby visible tiles snap edge-to-edge and align into rows or columns. Drag farther away to separate them. Tile snapping takes priority over grid snapping on release; hidden tiles are ignored. Text stays the same size as the chart expands. Mini mode shows only the header.

The **Coin** menu contains the top 100 coins by market capitalization in groups of 20; Discover's Crypto filter searches the same catalog. This is a CoinGecko USD ranking snapshot retrieved September 8, 2026, not a continuously reordered ranking. Duplicate ticker symbols have a rank suffix to distinguish the coins. Stablecoins and wrapped assets in the provider's top 100 are included.

Default keyboard shortcuts: **Ctrl+R** refresh, **Ctrl+P** pin, **1 / 2 / 3** chart range, **Ctrl+M** control panel, **Alt+F4** close widget.

## Market data and calculations

BTC, ETH, SOL, DOGE, XRP, and ADA use public Coinbase Exchange data. The other bundled coins use [CoinGecko](https://www.coingecko.com/en/api) price data. Stocks and other market symbols use Yahoo Finance's public search/chart endpoints. Requests and responses were verified during development, but Yahoo's public endpoints are unofficial and can change or become unavailable. The app displays unavailable/stale states and retries instead of supplying synthetic prices.

Widgets request quotes every 15 seconds and chart history every five minutes, or immediately after a range change. CoinGecko quotes are shared and cached for two minutes; its month history is cached for five minutes and filtered for 1D / 1W / 1M (usually hourly samples). Requests are spaced out to respect public API limits, so a newly added coin can take a few seconds to load. Rate limits show an unavailable/stale state and retry automatically. CoinGecko history does not provide per-candle volume bars. The panel refreshes prices every minute. Requests run asynchronously; selection changes cancel older widget requests. News is loaded from Yahoo's RSS feed and can be refreshed on Overview. Headlines link to their publishers.

For stocks, funds and indices, the 1W view shows the latest five trading sessions. Closed-market gaps are compressed in every range so the line fills the available width; labels, hover and volume follow actual market samples. The bottom labels show real trading dates in the PC's local timezone. Crypto retains five consecutive calendar days ending today, including its real weekend prices. No future prices are added. Crypto's other ranges are rolling 1 / 30 days; other assets use a session / month. If the current day has no candles, a one-day chart falls back to the last available session. Yahoo charts use 5-minute samples for 1D, 30-minute samples for 1W, and 180-minute samples for 1M, with pre-market and after-hours data enabled. Monthly samples group 30-minute feed bars into three-hour periods, retaining the final price and total volume, including the latest partial period. Available newer extended-session prices also update the header; the provider tooltip identifies extended hours. Some indices provide only limited late-session updates, so extended trading data may remain sparse or unavailable. Charts use sampled candles plus the latest available quote, so gaps or delays from the source can remain visible. Intraday Yahoo points use the source's bucket timestamp; Coinbase points use the bucket close. The top-right percentage in the 1W view compares the first and last visible plotted prices; other ranges compare the first visible plotted price with the latest quote. Changing the selected range changes this comparison. Arrow direction and chart color use the same return. If chart data is unavailable, the percentage displays a dash. Chart currency follows the feed. Three rounded price references on the left align with horizontal gridlines. The gridlines stay at 10%, 50% and 90% of the chart height. References use round multiples of intervals such as 5, 100 or 5,000, with decimal steps for small prices. The scale adjusts to fit all visible prices; the interval and decimal precision follow the visible price range.

The panel's movers compare against the previous daily close (rolling 24-hour opening price for Coinbase crypto). They are ranked within the fetched reference/tracked symbols, not the entire market. Closed markets are shown with their last available trade time. Futures and forex quotes are for display; the portfolio does not calculate futures contract multipliers or currency conversion.

Portfolio totals use USD-denominated positions and average-cost accounting, including fees. Missing or unusable USD quotes leave valuation totals unavailable. The **1D price P&L** is price movement multiplied by the quantity currently held; it does not reconstruct intraday positions. Total P&L includes realized gains, unrealized gains, and cash dividends. This is a personal tracker, not a tax-accounting engine.

Upcoming events is a manual personal calendar, not an automatic earnings/economic feed or notification service. No startup registration, cloud sync, subscription, or paid feature system is installed.

## Saved data

**Save current setup** in **Desktop** stores a separate snapshot of your tiles, their positions, sizes, chart ranges, visibility, pin/lock settings, colors and other widget preferences. **Load saved setup** restores that snapshot, reopens closed tiles and removes tiles added since it was saved. Moving, resizing or closing tiles does not overwrite the snapshot. Saving again replaces it. It survives quitting and reopening the app. Portfolio transactions and calendar entries are not part of the snapshot and remain unchanged when loading it. If a monitor is disconnected, restored tiles are kept on an available screen.

Widgets, layout, colors, shortcuts, calendar entries and transactions are saved beside the executable in **workspace.json**, with the previous save in **workspace.json.bak**. The first version's **settings.json** is imported on the first launch of version 2 and left in place. A damaged workspace is preserved with an `.unreadable-<timestamp>` suffix before a fresh workspace is used. Copy the executable and workspace into a writable folder for a portable copy.


## Downloads, updates and support

Download the Windows installer or portable ZIP from [Glance Finance Releases](https://github.com/Brusko25/Glance-Finance-Releases/releases/latest).
GitHub's automatic Source code archives contain release documentation, not the app.
Use **Check for updates → Update now** for future releases. To install manually, use **Quit**, back up workspace.json, and run the new installer over the same installation, or replace the executable and documentation in a portable folder. Neither package contains user data. The installer defaults to `%LOCALAPPDATA%\Programs\Glance Finance`. Uninstalling removes installed program files and shortcuts but preserves workspace files; delete those yourself only if you want to remove your data. Moving from an existing portable folder requires copying its workspace.json into the installed app folder while the app is closed. The application and installer are unsigned.

Report problems through [GitHub Issues](https://github.com/Brusko25/Glance-Finance-Releases/issues).
Include the app version (shown under About), Windows version, reproduction steps,
and exception text if present. Remove personal paths and portfolio information.
Do not attach workspace.json, settings, backups or account credentials.

Existing Glance Finance installations keep their original installation folder during upgrades. The executable remains named GlanceFinance.exe for compatibility with existing workspaces and shortcuts.

Version 2.4.0 mistakenly used the Glance LLM Usage name. Version 2.4.1 restores Glance Finance. Upgrade the finance app with the finance installer even if its old folder is named Glance LLM Usage. The separate usage widget has its own installer and settings.


## Checking for new versions

The app checks its public GitHub releases shortly after startup and daily. Choose **Check for updates** from the workspace, widget or tray menu. When a newer stable version is available, choose **Update now** to download and verify it, save and back up your workspace, update the existing copy, and restart. **Not now** leaves the app unchanged; downloads can be cancelled.

Installed copies use the Windows installer in their existing folder. Portable copies replace only the executable and bundled documentation, with rollback if replacement fails. Your tiles, saved setup, portfolio and calendar stay in workspace.json. A timestamped workspace.json.before-update backup is kept beside it. Update checks and downloads send no account credentials or workspace data.

Version 2.6.0 and earlier need one manual installation of a version containing this updater. After that, updates can be installed from inside the app. Weekly charts use short weekday labels such as Thu, Fri and Mon; stock charts still skip closed-market days.
