# Testing Log

**Goal:** check that changing `selected_income` updates the title, table, and chart, and the caption stays accurate.

**Command (GitHub Codespace, repository root):** `quarto render assignments/assignment07-dashboard/submission/dashboard.qmd`

1. **2026-11-05, `"Low Income (<1.3)"`:** rendered 11 cycles (no 2019-2020) with the full caption.
2. **2026-11-05, `"Middle Income"`:** title and values changed; caption still accurate. My first try, `"Middle Income (<1.3)"`, was not a valid value, so the dashboard switched to "High Income (>3.5)" without an error. The title showed the wrong group, so I fixed the value.
3. **2026-11-06, back to `"Low Income (<1.3)"`:** after the final text edits, values matched step 1, so only text changed.