# HANDOVER_LOG.md

<!--- -------------------------------------------------------------------------
This is a template, so ensure you remove instructions, such as these comments
and all material not task-relevant before the final commit.
-------------------------------------------------------------------------- --->

## Handover log

Each entry is added by the handover recipient after attempting to reproduce the repo outputs using only the README.

Template (copy and fill in):

- Date:
- Recipient:
- Repo tested (URL or repo name):
- OS:
- R version:
- RStudio version (optional):
- Step 1: renv::restore() (PASS/FAIL):
- Step 2: render report (PASS/FAIL):
- Command used to render:
- Outputs created (list files that exist):
- If FAIL: error message (copy exact message):
- One improvement suggestion for README/repo:

---

## Example entry (PASS)

- Date: 2026-01-25
- Recipient: Student B
- Repo tested: st422-week3-starter-repo
- OS: Windows 11
- R version: 4.3.2
- RStudio version (optional): 2023.12.1
- Step 1: renv::restore() (PASS/FAIL): PASS
- Step 2: render report (PASS/FAIL): PASS
- Command used to render: rmarkdown::render("reports/week3_report.Rmd")
- Outputs created (list files that exist):
  - outputs/tables/table1.csv
  - outputs/figures/churn_by_plan.png
  - outputs/figures/nps_by_churn.png
- If FAIL: error message (copy exact message): N/A
- One improvement suggestion for README/repo:
  - Add a short "Expected outputs" section with the file names and locations.

---

## Example entry (FAIL)

- Date: 2026-01-25
- Recipient: Student A
- Repo tested: st422-week3-example
- OS: macOS 15
- R version: 4.4.1
- RStudio version (optional): 2024.04.2
- Step 1: renv::restore() (PASS/FAIL): PASS
- Step 2: render report (PASS/FAIL): FAIL
- Command used to render: rmarkdown::render("reports/week3_report.Rmd")
- Outputs created (list files that exist):
  - outputs/tables/table1.csv
- If FAIL: error message (copy exact message):
  - Error: 'data/raw/st422_week3_subscription_v1.csv' does not exist in current working directory ('.../reports')
- One improvement suggestion for README/repo:
  - Add knitr root directory setting in the setup chunk so paths resolve from the repo root.