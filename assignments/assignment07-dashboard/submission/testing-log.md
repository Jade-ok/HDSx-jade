# Testing Log

Command (GitHub Codespace, repository root): `quarto render assignments/assignment07-dashboard/submission/dashboard.qmd`

- **2026-11-05, `selected_income <- "Low Income (<1.3)"`:** rendered 11 cycles (no 2019-2020) with the full caption.

- **2026-11-05, `selected_income <- "Middle Income"`:** title and all 11 values changed; the y-axis again did not start at zero, so the caption stayed accurate. An input error, `"Middle Income (<1.3)"`, silently showed "High Income (>3.5)"; I caught it from the title. On 2026-11-06, the same filter in `Rscript` showed the smallest cycle had 1,327 people.

- **2026-11-06, back to `"Low Income (<1.3)"`:** after the text updates, values matched the first render (28.8 to 30.4) and `dashboard-preview.png`.