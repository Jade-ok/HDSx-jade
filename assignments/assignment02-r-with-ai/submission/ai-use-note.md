# AI-Use Note

## Audit trail

```r
# AI prompt: "Among adults 20+, mean BMI by Cycle with n and missing count, plus change from the first cycle"
# Verified: column names match names(nhanes); n across cycles adds up to 58,462,
#           which equals nhanes |> filter(Age >= 20) |> nrow(); na.rm = TRUE is used

# AI prompt: "summary_table.csv shows -0.1999999999999993. Fix it in the code, not the file"
# Verified: after rounding, summary_table.csv shows -0.2, 0.4, ... and matches bmi_summary

# AI prompt: "Turn my adult BMI-by-cycle summary into a function that works for any numeric column"
# Verified: summarise_by_cycle(nhanes, "BMI") gives the same n, missing counts,
#           and means as bmi_summary in the Summarize section

# AI prompt (GitHub Copilot Chat): "Explain what this function does, line by line. Keep it short."
# Verified: compared each line of the explanation with the code, and checked it against
#           the BMI output table (n, n_missing, mean_value)
```

## What AI helped with
I chose my question (did adult mean BMI increase across survey cycles?) and 
asked Claude to design the code for it and turn it into the function summarise_by_cycle().
I used GitHub Copilot Chat to explain the function line by line.

## What I changed
Claude said most people missing Education were children, but when I checked their ages
with code they ranged from 0 to 85, so I removed that claim.
The AI-drafted code saved long decimals such as -0.1999999999999993 in summary_table.csv,
so I added rounding to change_from_first in the code instead of editing the CSV.

## How I verified the result
I checked that n across all cycles adds up to the number of adults (58,462)
and that the function gives the same results as bmi_summary for BMI.
I compared Copilot's line-by-line explanation with the code and the BMI output table.