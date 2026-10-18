# AI-Use Note

## Audit trail

```text
# AI prompt: I have r_summary in polyglot-parity.qmd and py_summary in translation.ipynb.
#   I expect the IncomeGroup and Gender labels to be the same and in the same order.
#   Can you write a Python cell that confirms that and returns True or False? Copy the R labels from r_summary.
#   Do not change py_summary.
# Verified: returned True; also compared the labels by eye with r_summary

# AI prompt: Same check for n, mean_bmi, and sd_bmi after rounding to 2 decimals.
#   Return True or False.
# Verified: returned True; also compared the values by eye with as.data.frame(r_function_summary)

# AI prompt: Run Cell in polyglot-parity.qmd shows "R session did not attach, so code was not sent".
#   How can I run the R chunks and see the output?
# Verified: ran quarto render as suggested; it finished with no error and the HTML showed
#   the output of every R chunk, including the parity checks (105626, 18, 87647, 6)
```

## What AI helped with
I used AI to find the textbook code for each task, to write the label and value comparison
cells in `translation.ipynb`, and to explain why Run Cell failed and how to render the qmd instead.
It also drafted the notes in `parity-table.csv` and `dependency-note.md`.

## What I changed
In `translation.ipynb`, AI's first parity check cell printed the Python group labels as one
long list, which was hard to compare with the R table. To compare them at a glance, I asked AI
for a cell that copies the R labels from r_summary into the notebook and confirms that they match
the Python labels.

## How I verified the result
R and Python match on row counts (105,626), columns (18), filtered rows (87,647), groups (6),
group labels, and rounded n, mean_bmi, and sd_bmi.