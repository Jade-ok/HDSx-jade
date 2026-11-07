# AI Use Note

I used Claude and GitHub Copilot Chat while working on this assignment.

## Audit trail

```text
# AI prompt: rewrite the plot caption in plain language for a new health reporter; keep unweighted, ages 20-80, exclusions, the missing 2019-2020 cycle, the y-axis not starting at zero, and non-causal framing
# Verified: each claim matches the summary table and plot; still accurate after switching to "Middle Income"
```

## What AI Helped With and What I Changed

- **Audience:** Claude suggested audience options; I chose a new health reporter, drawing on my experience as a news editor.
- **Caption (`dashboard.qmd`):** Claude drafted wording options. I rejected drafts that used jargon or over-explained survey design, and set the final content: plain-language scope, the unweighted disclosure, exclusions, the missing 2019-2020 cycle, the y-axis warning, and non-causal framing. Claude helped fix the R syntax with `paste0()` and flagged that a hard-coded group name would be wrong when the control changes.
- **Reader check (`dashboard.qmd`):** I asked Copilot Chat to review the graph from the view of a new reporter who received it in a press package. I adopted its point that the "<1.3" income label needed a plain explanation and added one to the caption. It also suggested a headline saying mean BMI "rose 1.8 points" and adding the first and last values as text on the plot. I did not adopt either. The 1.8 figure comes from 28.6 and 30.4, which are the lowest and highest cycles, not the first and last (the first cycle, 1999-2000, is 28.8), so the headline misreads the data and overstates a trend. I also kept my change to the caption text and left the plot itself as it was.
- **Notes (`.md` files):** Claude helped draft and edit wording. I decided the content and added two limitations based on TA feedback for previous assignments (different people in each cycle; self-reported income).

## How I Verified It

I checked every caption and interpretation claim against the rendered table and figure (11 cycles, no 2019-2020, values from 28.6 to 30.4, y-axis starting near 28.5) and re-rendered with "Middle Income" to confirm the caption still held. I also checked that the revised wording does not imply causality, population inference, or access to row-level data.

## Data Shared

Only aggregated summaries (the summary table, rows per cycle, and the income-ratio range of each group), chart screenshots, and the rendered HTML; no row-level data.