# Before / After Text

**Location:** `labs(caption = ...)` in the `dashboard-plot` chunk of `dashboard.qmd`.

**Original:**
"Descriptive, unweighted classroom summary. Missing BMI, income group, cycle, and out-of-cohort ages are excluded."

**Revised:**
"Mean BMI among adults aged 20-80 in a classroom NHANES dataset. The data have not been adjusted to reflect the U.S. population, so the results do not represent all U.S. adults. People with missing BMI, income group, or survey cycle data were excluded. The 2019-2020 cycle is missing due to COVID-19 disruptions. The y-axis does not start at zero, making small changes look larger. The chart shows patterns, not causes."

**Why it helps:** A new health reporter can now read, directly under the chart, what the data cover and which claims they do not support: no national claims, no causal claims, no missing the gap in cycles, and no exaggerating a small change.

**No analytic logic changed:** Only the caption string was edited (wrapped in `paste0()` for line breaks); the filter, summary, and plot code are unchanged, and the plotted values match the original render.

**Other text updated:** The Audience, Question, Interpretation, and Limitation text in `dashboard.qmd` were updated to match my notes.