# Dashboard Adaptation Note

## Audience

A new health reporter who receives this dashboard as part of a press package and needs to decide which statements about income and BMI are safe to report.

## Dashboard Question

For the income group I am writing about, how did mean BMI among adults aged 20-80 change across NHANES survey cycles in this classroom dataset, and how large was that change?

## Control And Visualization

- Control or interaction: the `selected_income` value in the Control chunk. Valid values are "Low Income (<1.3)", "Middle Income", and "High Income (>3.5)".
- Visualization affected: the line chart of mean BMI by NHANES cycle, and the summary table above it.
- What changes when the control changes: the filter keeps only the chosen income group, so the table values, the plotted points, and the chart title all update.

## Changed Element

I rewrote the figure caption. A reporter often copies only the chart into a story, so the caption is the one place where warnings travel with the figure. The original caption used terms a new reporter may not know ("unweighted", "out-of-cohort ages"), did not explain the income label in the title, and did not mention the missing 2019-2020 cycle or the y-axis that does not start at zero. I learned to check for these two figure issues in Assignment 5, where I fixed the y-axis in code; here I flagged both in the caption without changing the plot.

## Before And After

| Original text | Revised text | Why the revision helps |
|---|---|---|
| Descriptive, unweighted classroom summary. Missing BMI, income group, cycle, and out-of-cohort ages are excluded. | Adults aged 20-80 in a classroom NHANES dataset. Income group = family income relative to the U.S. poverty line; <1.3 means below 1.3 times the poverty line. Results are unweighted and not adjusted to the U.S. population, so they do not represent all U.S. adults. Missing BMI, income, or cycle data were excluded. The 2019-2020 cycle is missing because of COVID-19. The y-axis does not start at zero, so small changes can look larger. This shows patterns across survey cycles, not changes within the same people or causal effects. | It explains the income label and jargon in plain words, and warns against the four mistakes a reporter is most likely to make: national claims, causal claims, missing the gap in cycles, and exaggerating a change of under 2 BMI units. |

## Test Result

The dashboard rendered with "Low Income (<1.3)" and "Middle Income". The title, table, and points updated each time, and the caption stayed accurate. One input error ("Middle Income (<1.3)") silently switched the view to "High Income (>3.5)"; I caught it from the title and fixed it. See `testing-log.md`.

## Limitation

This dashboard shows unweighted, descriptive mean BMI for adults aged 20-80 in a classroom NHANES dataset, so it does not represent all U.S. adults and cannot show that income causes changes in BMI. NHANES surveys different people in each cycle, so the line compares groups over time, not changes within the same people. Income group is based on self-reported family income, so some people may be placed in the wrong group. The core limits also appear in the figure caption ("they do not represent all U.S. adults", "not changes within the same people or causal effects").

## Privacy Check

The dashboard shows only counts and mean BMI for each survey cycle, never individual records. In the submitted Low Income view, the smallest cycle has 1,089 people, so no mean is based on a very small group. The caption states that the chart shows patterns, not causes.