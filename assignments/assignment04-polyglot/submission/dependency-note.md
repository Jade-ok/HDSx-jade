# Dependency Note

## R
- tidyverse: `readr::read_csv()` loads the CSV; `dplyr` (`filter`, `group_by`, `summarise`, `arrange`) builds the summary.

## Python
- pandas: `read_csv`, `dropna`, `groupby`, `agg`, `sort_values`, `round` build the same summary.
- pathlib: checks that the CSV file exists in `helpers.py`. It is part of the Python standard library, so no install is needed.

No packages were added beyond the course Codespace baseline, so `.devcontainer/requirements.txt` was not changed.