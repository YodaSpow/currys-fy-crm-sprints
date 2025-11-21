# Currys FY Sprint Calendar – Config Guide

This project reads settings from `data/config.json`. Use ISO dates (`yyyy-mm-dd`) and keep edits to the noted keys.

⚠️ Annual reminder (April): each new FY, update the 3 required fields in `data/config.json` — `fy_start_year`, `weeks.wk1_saturday` (WK1 Saturday), and `sprint.first_sprint_start` (Sprint 1 Monday). If Currys changes the anchor dates, refresh these values before serving the calendar.

## Quick edits (what to change)
- ✏️ `notes.required_edit_1` → `fy_start_year`: financial year start (May belongs to this year).
- ✏️ `notes.required_edit_2` → `weeks.wk1_saturday`: ISO date for WK1 Saturday (e.g., `2025-05-10` = 10/05/2025 UK).
- ✏️ `notes.required_edit_3` → `sprint.first_sprint_start`: ISO date of Sprint 1 Monday (e.g., `2025-08-04` = 04/08/2025 UK).

## Field reference
- `fy_start_year`: first year of the FY (May–Apr).
- `weeks.wk1_saturday`: anchor Saturday for WK 1 (ISO). Drives week numbering.
- `sprint.length_weeks`: sprint length in weeks (default 2).
- `sprint.first_sprint_start`: first sprint start Monday (ISO). Drives sprint labels.
- `quarters_periods`: maps months into Q/P labels.
- `display.first_month` / `display.last_month`: calendar range (FY May→Apr).
- `display.colour_seed`: palette offset for sprint colours (integer).
- `bank_holidays.enable_live`: fetch UK bank holidays from gov.uk.

## 🎨 Sprint colour palette
Used in `index.html` (`sprintColours`). Colours cycle with an offset from `colour_seed`:
1. `#6ac8ff` (sky blue)
2. `#7fd6a6` (mint)
3. `#ffc27a` (amber)
4. `#f39bd1` (pink)
5. `#9ea6ff` (periwinkle)
6. `#9ee1ff` (light aqua)
7. `#b4f0b4` (pale green)
8. `#ffd6a1` (peach)
9. `#ffb0b0` (soft red)
10. `#c9adff` (lavender)
11. `#98e0cb` (seafoam)
12. `#e7ffa3` (pale yellow)

`colour_seed` can be any integer; it’s taken modulo 12 to choose the starting colour. “Modulo 12” means it wraps every 12 steps (e.g., 12 acts like 0, 13 like 1). Default is **7** (what you see now). For quick changes, try 0, 3, 6, 9, or 11. If you want totally new colours, edit the `base` array inside `sprintColours` in `index.html`.

## Tips (layperson)
- Dates must be `yyyy-mm-dd` even if you think in `dd/mm/yyyy`; the example `2025-05-10` equals 10/05/2025 UK.
- Change only the three required edits for a new FY: `fy_start_year`, `weeks.wk1_saturday`, and `sprint.first_sprint_start`.
- If sprint colours feel repetitive, change `colour_seed` to another number; no other steps needed.
- Avoid editing below `meta_do_not_edit_below` unless you know the logic.
