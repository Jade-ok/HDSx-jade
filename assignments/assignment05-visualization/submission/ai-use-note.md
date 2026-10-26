# AI-Use Note

## Audit trail

```text
# AI prompt: change the income summary to gender, adults 20-80, all cycles
# Verified: 22 rows (11 cycles x 2 genders); the smallest group has 1,923 people

# AI prompt: line plot of mean BMI by cycle, one line per gender, y-axis from 0
# Verified: 22 points match bmi_by_gender; lines look almost flat

# AI prompt: x-axis labels overlap and the lines look flat with the y-axis at 0. fix both
# Verified: x-axis labels are readable after rotating; I compared the plot with y from 0 and from 27 and kept 27 because the ups and downs were visible; points match bmi_by_gender
```

## What AI helped with
Claude suggested questions to guide the audit of the flawed plot, drafted the ggplot2 code for the summary and plots, and drafted the text of the Quarto file and notes. It also turned my audit findings into a Markdown table.

## What I changed
Claude first suggested repeating the worked example's income comparison, but I chose gender instead because Gender has no missing values and both groups are large in every cycle. My draft started the y-axis at 0, but the lines looked flat and hid the changes across cycles, and the x-axis labels overlapped, so I asked for both to be fixed; I kept the zoomed 27-31 range and explained the choice in the caption. I found the audit issues by comparing the flawed plot with its code, and Claude turned my findings into a table of seven issues with long, packed sentences; I kept the four that change what the plot claims and rewrote each one so the problem is stated plainly.

## How I verified the result
I ran each audit check on the real data in Codespaces: the youngest age was 2, 50% of Low Income was under 20, there are 11 cycles, and with adults only the income order flips. I reread the audit note against `flawed-plot-code.R`: I checked that the quoted title and subtitle match the code word for word, made each issue say where the problem is in the code, and removed claims I had not checked myself. For my own plot, I checked that the code uses the real column names (`BMI`, `Age`, `Gender`, `Cycle`), that 1,009 of 57,137 adults had missing BMI, that the summary has 22 rows with the smallest group at 1,923 people, and that the plotted points match the summary table. I compared the y-axis from 0 and from 27 before choosing 27, and I checked that the title and caption make no causal or population-level claim and state that the summary is unweighted.