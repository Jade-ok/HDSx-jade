# AI-Use Note

## Audit trail
# AI prompt: ggplot2 bar chart of mean BMI by income group, with labels
# Verified: column names against names(nhanes); compared means with summary()

## What AI helped with
Copilot drafted the initial ggplot2 code for the income-group plot and
suggested axis label wording.

## What I changed
The draft used a column called "income" that does not exist; I replaced it
with IncomeGroup. I also removed a misleading y-axis limit it added.

## How I verified the result
I re-ran the summary statistics without the plot and checked that the bar
heights match the group means; I confirmed the caption says the result is
descriptive and unweighted.