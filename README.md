# Phenolics & Antioxidant Assay Calculator

Interactive, browser-only calculator for:

- **Content assays:** Total Phenolic Content (TPC), Total Flavonoid Content (TFC), Total Tannins, FRAP
- **Radical scavenging assays:** DPPH, ABTS, H₂O₂, hydroxyl (OH)

Features: triplicate standard curves with linear regression (slope, intercept, R²), mean ± SD for every sample,
% scavenging with IC50 and relative potency, live plots (standard curves, dose–response with error bars,
summary bar charts), CSV export, print/PDF. Data stay in your browser (localStorage); nothing is uploaded.

No build step, no dependencies: it is a single `index.html`.

## Run locally
Open `index.html` in any modern browser (or `python3 -m http.server` and visit http://localhost:8000).

## Publish on GitHub Pages
1. Create a new repository on GitHub (e.g. `phenolics-calculator`) and upload `index.html` and this README
   (or `git init`, `git add .`, `git commit`, `git remote add origin <url>`, `git push -u origin main`).
2. In the repository: **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
   choose branch `main` and folder `/ (root)`, then **Save**.
3. After about a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

## Formulas
- Standard curve: `Abs = m·Conc + c` (least squares); Conc = (Abs − blank − c) / m
- Content per g extract = Conc × DF × V(mL) / W(mg)
- % scavenging = (A_control − (A_sample − colour blank)) / A_control × 100
- IC50 = (50 − c) / m from regression of mean % vs concentration (use the linear range that brackets 50 %)
- Relative potency = IC50 standard / IC50 sample

Example values shown on first load are placeholders, not real data. Check the OH and H₂O₂ formulas against your
protocol (they assume absorbance decreases as scavenging increases).
