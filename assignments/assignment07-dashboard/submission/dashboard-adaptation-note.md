# Dashboard Adaptation Note

## Audience

A new health reporter who receives this dashboard as part of a press package and needs to decide which statements about income and BMI are safe to report.

## Dashboard Question

Among adults age 20-80, how does mean BMI vary across NHANES cycles for one selected income group?

## Control And Visualization

- Control or interaction: the `selected_income` value in the Control chunk. Valid values are "Low Income (<1.3)", "Middle Income", and "High Income (>3.5)".
- Visualization affected: the line chart of mean BMI by NHANES cycle, and the summary table above it.
- What changes when the control changes: the filter keeps only the chosen income group, so the table values, the plotted points, and the chart title all update.

## Changed Element

I rewrote the figure caption. A reporter often copies only the chart into a story, so the caption is the one place where warnings travel with the figure. The original caption used terms a new reporter may not know ("unweighted", "out-of-cohort ages") and did not mention the missing 2019-2020 cycle or the y-axis that does not start at zero. I learned to check for these two issues in Assignment 5, where I worked with the same dataset and noted both in my own caption. In A7 I did not change the plot code; I explained the issues in the caption instead.

## Before And After

| Original text | Revised text | Why the revision helps |
|---|---|---|
| Descriptive, unweighted classroom summary. Missing BMI, income group, cycle, and out-of-cohort ages are excluded. | Mean BMI among adults aged 20-80 in a classroom NHANES dataset. The data have not been adjusted to reflect the U.S. population, so the results do not represent all U.S. adults. People with missing BMI, income group, or survey cycle data were excluded. The 2019-2020 cycle is missing due to COVID-19 disruptions. The y-axis does not start at zero, making small changes look larger. The chart shows patterns, not causes. | It replaces jargon with plain words and warns against the four mistakes a reporter is most likely to make: national claims, causal claims, missing the gap in cycles, and exaggerating a change of about 2 BMI units. |

## Test Result

The dashboard rendered with "Low Income (<1.3)" and "Middle Income". The title, table, and points updated each time, and the caption stayed accurate. One typo ("Middle Income (<1.3)") silently switched the view to "High Income (>3.5)"; I caught it from the title and fixed it. See `testing-log.md`.

# Limitation

This dashboard shows unweighted, descriptive mean BMI for adults aged 20-80 in a classroom NHANES dataset, so it does not represent all U.S. adults and cannot show that income causes changes in BMI. NHANES surveys different people in each cycle, so the line compares groups over time, not the same people getting heavier. The same core limits appear in the figure caption ("the results do not represent all U.S. adults", "the chart shows patterns, not causes").

## Privacy Check

The dashboard shows only counts and mean BMI for each survey cycle, never individual records. In the submitted Low Income view, the smallest cycle has 1,089 people, so no mean is based on a very small group. The caption states that the chart shows patterns, not causes.