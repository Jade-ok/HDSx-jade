# Before / After Text

**Location:** `labs(caption = ...)` in the `dashboard-plot` chunk of `dashboard.qmd`.

**Original:**
"Descriptive, unweighted classroom summary. Missing BMI, income group, cycle, and out-of-cohort ages are excluded."

**Revised:**
"Adults aged 20-80 in a classroom NHANES dataset. Income group = family income relative to the U.S. poverty line; <1.3 means below 1.3 times the poverty line. Results are unweighted and not adjusted to the U.S. population, so they do not represent all U.S. adults. Missing BMI, income, or cycle data were excluded. The 2019-2020 cycle is missing because of COVID-19. The y-axis does not start at zero, so small changes can look larger. This shows patterns across survey cycles, not changes within the same people or causal effects."

**Why it helps:** A new health reporter can now read, directly under the chart, what the income label means, what the data cover, and which claims they do not support: no national claims, no causal claims, no missing the gap in cycles, and no exaggerating a small change.

**No analytic logic changed:** Only the caption string was edited (wrapped in `paste0()` for line breaks); the filter, summary, and plot code are unchanged, and the plotted values match the original render.

**Other text updated:** The Audience, Question, Interpretation, and Limitation text in `dashboard.qmd` were updated to match my notes.