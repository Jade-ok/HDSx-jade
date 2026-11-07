# AI Use Note

I used Claude (an AI assistant) in a chat while working on this assignment.

## What AI Helped With, By Prompt

- "Check the Nov 3 lecture notes and tell me what I need to do in my forked repo." AI summarized the A7 instructions and the nine required files.
- "What other audience examples are there?" AI suggested several audiences; I chose a new health reporter, based on my own work as a news editor.
- "Write the caption." AI drafted the first caption in `dashboard.qmd`.
- "This doesn't explain what 'unweighted' means." and "This explanation is also strange." AI revised the wording twice; I then wrote my own caption.
- "How about this?" (my caption draft) AI found that my Python-style string joining fails in R and that "low-income" was hard-coded, so the caption was rewritten with `paste0()` and the group name removed.
- "Error in parse ... unexpected end of input." AI explained the missing `)` after `paste0()`.
- AI drafted all seven `.md` notes; I asked for a translation and review of each and revised them (for example, the dashboard question, the Limitation text based on TA feedback from my Data Intake Card and Milestone 1, and the length of the brief notes).

## How I Verified It

I checked every caption and interpretation claim against the rendered table and figure (11 cycles, no 2019-2020, values from 28.6 to 30.4, y-axis starting near 28.5) and re-rendered with "Middle Income". I also checked that the revised wording does not imply causality, population inference, or access to row-level data. To confirm that each cycle has different people, AI read only the column names and per-cycle row counts of the local data file.

## Data Shared

Only the aggregated summary table, chart screenshots, and the rendered HTML; no row-level data.