# Testing Log

- **Date:** 2026-11-05, GitHub Codespace, from the repository root.
- **Command:** `quarto render assignments/assignment07-dashboard/submission/dashboard.qmd`
- **Run 1 (Low Income (<1.3)):** first render failed with "unexpected end of input" because the closing `)` of `paste0()` was missing. After adding it, the render succeeded: title "Mean BMI for Low Income (<1.3)", 11 rows (no 2019-2020 cycle), caption fully visible.
- **Run 2 (Middle Income):** render succeeded. Title changed to "Mean BMI for Middle Income", table values changed, smallest n = [ ], y-axis again did not start at zero, so the caption stayed accurate.
- **Run 3:** switched back to "Low Income (<1.3)" and re-rendered; output matches `dashboard-preview.png`.