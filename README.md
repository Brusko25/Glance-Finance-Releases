# Glance Finance

Public Windows downloads, release history and support for Glance Finance.
Application source and development history are maintained in the private
`Glance-Finance-Code` repository.

**[Download the latest Windows release](https://github.com/Brusko25/Glance-Finance-Releases/releases/latest)**

A compact desktop finance app with floating market widgets and a dark control
panel. Track stocks, funds, indices, futures, forex and crypto; organize widgets;
and keep a local record of your USD investments.

## Get started

1. Download `Glance-Finance-v2.0.1-Windows.zip` from the release page.
2. Extract it into a writable folder on Windows 10 or 11 with .NET Framework 4.8.
3. Run **GlanceFinance.exe**. No account, API key or terminal is required.
4. Use **Home** to search a company/symbol and add desktop widgets.

The current executable is unsigned. The download includes `SHA256SUMS.txt` as a
separate release asset for checking the ZIP's integrity. GitHub's automatic
Source code archives contain this repository's documentation, not the app.

## What's included

| Page | Controls |
| --- | --- |
| Home | Asset search, category filters, news, tracked movers and manual calendar dates |
| Portfolio | Local buys/sells/dividends, holdings, average cost and P&L |
| Update Layout | Resize, grid, alignment, mini mode, locking and mouse click-through |
| Color Settings | Foreground/background palettes, opacity, price flashes and volume bars |
| Keybindings | Custom shortcuts for focused widgets |
| My Widgets | Show/hide, bring forward, remove, pin and select chart range |

Closing the panel keeps widgets running. Reopen it from the system tray or a
widget's menu. Use **Quit** to close the entire app.

See the **[User guide](USER_GUIDE.md)** for complete controls and data behavior.

## Your data and updates

Your workspace, portfolio and settings stay in `workspace.json` beside the app.
No trades are submitted. Quotes come from Coinbase Exchange and Yahoo Finance;
they can be delayed, unavailable or reflect a closed market. Yahoo's public
endpoints are unofficial. Portfolio totals support USD assets; calendar dates
are entered manually.

Updates are manual: use Quit, back up `workspace.json`, and extract the new
executable/documentation over the previous installation. Download ZIPs contain
no settings or workspace files. `version.json` is public release metadata;
this version does not have an automatic updater.

## Support and history

- [Report a bug or request a feature](https://github.com/Brusko25/Glance-Finance-Releases/issues)
- [Release history](RELEASES.md)
- [Changelog](CHANGELOG.md)

Include your app and Windows versions, steps to reproduce, and exception text
when reporting a bug. Remove personal paths and holdings from screenshots/logs.
Do not upload your workspace, settings, backups or credentials.
