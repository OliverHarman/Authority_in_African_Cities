# Authority in African Cities — RAI(Metro) Explorer

Interactive data explorer for metropolitan authority scores across seven African countries (1977–2025), built using the Regional Authority Index (RAI) framework.

Part of *Power and Place: Decentralisation and Urbanisation in Africa* by Oliver Harman.

Funded by the International Growth Centre (Project Grant XXX-24303).

## Live site

Once hosted, the site will be available at: `https://[username].github.io/[repo-name]/`

## Files

| File | Description |
|------|-------------|
| `index.html` | The complete interactive dashboard (single self-contained file) |
| `data.csv` | All country-year RAI(Metro) scores — **edit this to update data** |
| `README.md` | This file |

## How to update data

1. Open `data.csv` in Excel, Google Sheets, or any text editor
2. Each row = one country-year with all 10 RAI indicators
3. Columns: `Country, Region, Year, ID, PA, FA, BA, Rep, LM, EC, FC, BC, Const, SR, ShR, RAI`
4. To **add a new country or entity** (e.g. Kampala as a separate coding), just add rows with a new `Country` value — the site auto-detects it
5. To **update a year**, edit the relevant row
6. Commit and push — the site updates automatically

### Score formulas

- **Self-Rule (SR)** = ID + PA + FA + BA + Rep (max 18)
- **Shared Rule (ShR)** = LM + EC + FC + BC + Const (max 12)
- **Total RAI** = SR + ShR (max 30)

### Adding Kampala (example)

Add rows like this to `data.csv`:

```
Uganda - Kampala,KCCA,2010,2,3,2,2,3,0,0,1,0,3,12,4,16
Uganda - Kampala,KCCA,2011,2,3,2,2,3,0,0,1,0,3,12,4,16
```

The site will auto-detect "Uganda - Kampala" as a new entity and assign it a colour.

## Hosting via GitHub Pages

1. Create a new GitHub repository
2. Upload `index.html`, `data.csv`, and `README.md`
3. Go to **Settings → Pages**
4. Under **Source**, select **main** branch and **/ (root)** folder
5. Click **Save**
6. Your site will be live within a few minutes at `https://[username].github.io/[repo-name]/`

### Local development

To test locally (CSV loading requires a server):

```bash
python3 -m http.server 8000
# Then open http://localhost:8000
```

## RAI(Metro) Framework

The Regional Authority Index measures formal metropolitan authority across ten dimensions:

**Self-Rule** (authority exercised within the metropolitan unit):
- Institutional Depth (0–3)
- Policy Autonomy (0–4)
- Fiscal Autonomy (0–4)
- Borrowing Autonomy (0–3)
- Representation (0–4)

**Shared Rule** (participation in national decisions):
- Lawmaking (0–2)
- Executive Control (0–2)
- Fiscal Control (0–2)
- Borrowing Control (0–2)
- Constitutional (0–4)

Framework following Hooghe et al. (2016), *Measuring Regional Authority*, Oxford University Press.

## Citation

Harman, O., Hayward, J., & Sampó, G. (2026). Authority in African Cities. Working paper, International Growth Centre.
