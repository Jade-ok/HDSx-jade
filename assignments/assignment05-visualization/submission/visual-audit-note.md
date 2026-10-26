# Visual Audit Note

## Plot Question

The flawed plot asks how mean BMI differed by income group across NHANES cycles. My corrected plot asks how mean BMI differed between women and men aged 20-80 across all 11 NHANES cycles in the prepared class dataset.

## Issues Checked

| Issue | Category | Why it matters | Correction |
|---|---|---|---|
| The subtitle says "Adults age 20-80", but the `filter()` step in `flawed-plot-code.R` has no age condition, so people under 20 are included in the plot | Correctness | Children have lower BMI than adults, so including them changes the group means and the plot does not show the group its subtitle names | Filter `Age >= 20, Age <= 80` and state the age range in the subtitle |
| Only 2 of 11 cycles are plotted, so the plot shows no values between them and the reader cannot know the mean BMI in those years. Even so, the subtitle says BMI "climbed steadily across every NHANES cycle" | Correctness | The 9 middle cycles are hidden, so the reader cannot see dips (for example, 2011-2012) | Plot all 11 cycles with `geom_line() + geom_point()` |
| `scale_y_continuous(limits = c(24, 28))` cuts the y-axis with no note | Design | A reader may not notice right away that the y-axis starts at 24, not 0, so the plot is easy to misread. Also, when only adults are kept, many mean BMI values are above 28, so these values would fall out of range. | Use `coord_cartesian()` to set the y-axis range, and state the range in the caption so readers do not misread the plot |
| Title says "Low income drives rising obesity in American adults" | Interpretation | The plot shows a difference between groups, but it cannot show cause and effect. The data are unweighted, so they cannot speak for all US adults. The plot shows mean BMI, not obesity. | Use a title that only says what is plotted, and label the y-axis "Mean BMI (kg/m²)" |

## Final Caption

Mean BMI by gender across NHANES cycles, adults aged 20-80 in the prepared NHANES Health Equity class dataset. The summary is descriptive and unweighted. Records with missing BMI were excluded. There is no 2019-2020 cycle. The y-axis starts at 27 to show changes of about 1-2 BMI units. The plot shows patterns, not causal effects or population estimates.


## AI-Use Check

AI suggested questions to guide the audit and drafted ggplot2 code. I checked each issue by running code on the real data: the youngest age and the share under 20 by income group, the list of cycles, and adult-only means by income group. I also compared the flawed plot's title and subtitle with what the code actually does. After I drafted the Issues Checked section, I asked AI to turn it into a Markdown table and to polish the sentences. I then reread the table and revised the sentences myself.