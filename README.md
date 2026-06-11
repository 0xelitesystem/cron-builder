# cron-builder

Visual cron expression builder with human-readable description and the next 5 firing times. Single HTML file. Browser-only.

**Live demo:** https://0xelitesystem.github.io/cron-builder/

## Why

Cron syntax is one of those things you re-learn every time you need it. This tool keeps the syntax visible (good for learning) but adds a live description and a calendar of when it will actually fire (good for verifying).

## Use it

Open `index.html` in any browser, or visit the hosted demo at `https://0xelitesystem.github.io/cron-builder/` once Pages is enabled.

1. Edit the five fields directly (minute, hour, day-of-month, month, day-of-week).
2. The expression updates as you type.
3. The plain-English description updates with it.
4. Below, the next 5 firing times are calculated against your local time zone.
5. Click any of the 10 preset patterns to load it.

## Supported syntax

Standard 5-field cron:

| Field | Range | Notes |
|---|---|---|
| Minute | 0-59 | |
| Hour | 0-23 | |
| Day of Month | 1-31 | |
| Month | 1-12 | |
| Day of Week | 0-6 | 0 = Sunday |

Each field accepts:

- `*`, all values
- `5`, specific value
- `1-5`, range
- `*/15`, step (every 15)
- `1-10/2`, step within a range
- `1,3,5`, list

Combinations of these are supported.

## What it doesn't do

- Doesn't support 6-field cron (with seconds). Some systems (Quartz, Spring) use that variant; convert before pasting elsewhere.
- Doesn't support `L` (last), `W` (weekday), or `#` (nth weekday), these are Quartz extensions, not standard cron.
- Doesn't support named months (`JAN`, `FEB`) or named days (`MON`, `TUE`). Use numbers.
- Doesn't show what time zone the next-firings are in. They're shown in your browser's local time zone.
- Doesn't simulate cron behavior on systems with different semantics around DOM/DOW (some treat them as AND, some as OR, this tool uses AND).

## Tech

- Single HTML file, ~600 lines
- Vanilla JS, no frameworks, no dependencies
- Light and dark themes with OS preference detection
- WCAG AA contrast on both themes

## License

MIT. See [LICENSE](LICENSE).

## Related

- [csp-builder](https://github.com/0xelitesystem/csp-builder), build Content-Security-Policy headers visually
- [regex-tester-with-explainer](https://github.com/0xelitesystem/regex-tester-with-explainer), test and explain regex
- [csv-to-anything](https://github.com/0xelitesystem/csv-to-anything), convert CSV to JSON/SQL/Markdown/TS
