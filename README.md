![Currys CRM FY Sprint Calendar](assets/pageTitle.png)

Live demo: https://yodaspow.github.io/currys-fy-crm-sprints/

Static FY sprint calendar with week numbers, sprint bands, and UK bank holidays. Data is driven by `data/config.json` and `data/specials.csv`.

## Quick edits
- `data/config.json` (ISO dates `yyyy-mm-dd`)
  - `fy_start_year` (notes.required_edit_1)
  - `weeks.wk1_saturday` (notes.required_edit_2)
  - `sprint.first_sprint_start` (notes.required_edit_3)
- `data/specials.csv`: local specials/paydays (supports UK `dd/mm/yyyy` or ISO).

See `CONFIG.md` for detailed guidance, palette info, and annual reminders.

## Dev
```bash
# serve locally
bash Important.sh
# or
cd /Users/spowart/Documents/GitHub/currys-fy-crm-sprints && python3 -m http.server 8000
```

## Deploy (GitHub Pages)
- Branch: `main`, site at `https://yodaspow.github.io/currys-fy-crm-sprints/`.
- Relative fetches (`./data/config.json`, `./data/specials.csv`) work without CORS issues on Pages.
