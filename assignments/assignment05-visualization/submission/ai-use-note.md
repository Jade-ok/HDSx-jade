# AI-Use Note

## Audit trail

```text
# AI prompt: change the income summary to gender, adults 20-80, all cycles
# Verified: 22 rows (11 cycles x 2 genders); the smallest group has 1,923 people

# AI prompt: line plot of mean BMI by cycle, one line per gender, y-axis from 0
# Verified: 22 points match bmi_by_gender; lines look almost flat

# AI prompt: x-axis labels overlap and the lines look flat with the y-axis at 0. fix both without removing data
# Verified: x-axis labels are readable after rotating; I compared the plot with y from 0 and from 27 and kept 27 because the ups and downs were visible; points match bmi_by_gender
```

## What AI helped with
Claude suggested questions to guide the audit of the flawed plot, drafted the ggplot2 code for the summary and plots, and drafted the text of the Quarto file and notes.

## What I changed
I chose gender as my comparison. I noticed the x-axis labels overlapped and that the lines looked flat with the y-axis at 0, and I decided to zoom in to 27-31 and explain the choice in the caption. I rewrote the AI prompt comments so they match what I asked.

## How I verified the result
I ran each audit check on the real data in Codespaces: the youngest age was 2, 50% of Low Income was under 20, there are 11 cycles, and with adults only the income order flips. I checked that 1,009 of 57,137 adults had missing BMI, that the summary has 22 rows, and that the smallest group has 1,923 people.