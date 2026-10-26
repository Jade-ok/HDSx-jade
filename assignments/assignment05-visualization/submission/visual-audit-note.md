# Visual Audit Note

## Plot Question

The flawed plot asks how mean BMI differed by income group across NHANES cycles. My corrected plot asks how mean BMI differed between women and men aged 20-80 across all 11 NHANES cycles in the prepared class dataset.

## Issues Checked

| Issue | Category | Why it matters | Correction |
|---|---|---|---|
| Subtitle says "Adults age 20-80" but the filter has no age limit; the youngest person is 2. 50% of Low Income is under 20, compared with 31% of High Income | Correctness; Bias and aggregation | Children have lower BMI, so Low Income looks lowest because of age mix. With adults only, the order flips and High Income is lowest | Filter `Age >= 20, Age <= 80` and state the age range in the subtitle |
| Only 2 of 11 cycles are plotted, joined by a dashed line, while the subtitle says BMI "climbed steadily across every NHANES cycle" | Correctness | The 9 middle cycles are hidden, so the reader cannot see dips (for example, 2011-2012) | Plot all 11 cycles with `geom_line() + geom_point()` |
| `scale_y_continuous(limits = c(24, 28))` cuts the y-axis with no note | Design | A gap of about 3 BMI units looks huge. With adults only, the means are 27.9-30.4, so most points would fall outside this range | Use `coord_cartesian()`, which zooms without removing data, and state the axis range in the caption |
| Title says "Low income drives rising obesity in American adults" | Interpretation | "Drives" is a causal claim, and "American adults" is a population claim. An unweighted descriptive summary supports neither. The plot shows mean BMI, not obesity | Use a descriptive title and label the y-axis "Mean BMI (kg/m²)" |

## Final Caption

Mean BMI by gender across NHANES cycles, adults aged 20-80 in the prepared NHANES Health Equity class dataset. The summary is descriptive and unweighted. Records with missing BMI were excluded. There is no 2019-2020 cycle. The y-axis starts at 27 to show changes of about 1-2 BMI units. The plot shows patterns, not causal effects or population estimates.

## AI-Use Check

AI suggested questions to guide the audit and drafted ggplot2 code. I checked each issue by running code on the real data: the youngest age and the share under 20 by income group, the list of cycles, and adult-only means by income group.