# Git Audit Note

## Diff summary (AI-assisted, verified by me)

Added one line to the project map in `README.md` for `practice_report.html`.
`git status` showed only `README.md` as modified, and `git diff` showed one added line and no deleted lines.
No code lines were added or removed.

AI prompt and output I used:

```text
Prompt: I shared my terminal output (`git status` and `git diff`) with Claude and asked it to help draft a summary of the change.
AI output: Only README.md is modified. There is one added line (practice_report.html in the project map) and no deleted lines.
```

## .gitignore check

Confirmed secrets and temporary files are excluded. Required HTML remains committable.

## AI-use sentence

I used Claude to check my diff and draft the PR description and these notes.
I re-read the diff myself and confirmed the summary is accurate.

## M0 readiness

Our group repository is ready for M0.

- Members: Red Team, with Yoon Park (`yoon-cloud-28`), Humnah Rashid (`humnahr`), Jade Lee (`Jade-ok`), and Morgan Ehman (`m-ehman`, repository owner).
- Access: all four members confirmed that they can open the shared repository `m-ehman/SPPH-381H-Group3_Project`.
- Communication plan: our main channel is a private WhatsApp group chat. We reply within 24 hours on weekdays and 48 hours on weekends, and we check in for 10 minutes after Tuesday class.
- Codespaces access: all four members opened the group Codespace and confirmed that R, Quarto, and the tidyverse were available.