# HANDOVER_TEMPLATE.md

## Reproducibility Handover Check

This folder supports a structured handover test. The goal is to show that a peer can reproduce the project outputs using only the README.

### What the handover recipient will do

The recipient will:

1. Clone the repository to their machine.
2. Run the project using only the instructions in the README.
3. Record what happened in `handover/HANDOVER_LOG.md`.

### What counts as a successful handover

A handover is successful if the recipient can run the following from the project root:

- `renv::restore()`
- `rmarkdown::render("reports/week3_report.Rmd")`

and produce the expected outputs described in the README, for example:

- `outputs/tables/table1.csv`
- `outputs/figures/` (at least two figures)

### Rules for the recipient

- Follow the README exactly.
- Do not edit code unless the README instructs you to.
- If it fails, copy the error message and note the step where it failed.
- Provide one concrete improvement suggestion for the README or repo structure.

### Evidence policy (how we show the handover happened)

The handover is evidenced by:

- the recipient appending a new entry to `handover/HANDOVER_LOG.md`, and
- committing that change with the message: `Handover test by <name> (PASS/FAIL)`.

If the run fails, the repo owner should:

- fix the issue (README, code, renv, or paths),
- run `renv::snapshot()` if dependency changes were made,
- commit the fix with the message: `Fix handover issue: <short description>`, and
- rerun the render to confirm the fix.

---

## Common failure modes

### Missing packages

Symptom: "there is no package called ..."

Fix:

- install the package
- rerun the report
- run `renv::snapshot()` and commit `renv.lock`

### Wrong working directory (paths break)

Symptom: file does not exist, path includes `/reports`

Fix:

- set knitr root directory in setup chunk:
  - `knitr::opts_knit$set(root.dir = normalizePath(".."))`

### Outputs not created

Symptom: render succeeds but expected files are missing

Fix:

- ensure the report explicitly writes outputs:
  - `dir.create("outputs/tables", recursive = TRUE, showWarnings = FALSE)`
  - `write_csv(...)`
  - `ggsave(...)`

### Outputs policy confusion

Fix:
- ensure README clearly states whether outputs are committed or generated.