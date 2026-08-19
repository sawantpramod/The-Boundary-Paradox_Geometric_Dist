# Waiting for a Boundary in T20 Cricket
What Aggregate Waiting Times Can Hide

## Purpose
This project reproduces the useful parts of the supplied Jupyter notebook while **never deleting or overwriting the raw ball-by-ball data**.

The notebook's later cells **In [4] and In [5] (Weibull/Log-Logistic model comparison and hazard-model plotting)** are intentionally excluded, as requested.

## Data
Place the source file at:
`data/data-ball_by_ball.csv`

The supplied source file has 17,501 rows and 24 columns.

## Important analytical definitions
- An **attempt** is one legal delivery.
- A wicket event is `wicket_flag == True` on a legal delivery.
- A boundary event is `runs_off_bat` equal to **4 or 6** on a legal delivery.
- Non-legal deliveries are NOT deleted from the raw dataset. They are excluded only from analyses where the unit of analysis is a legal delivery.
- Innings with no first event are treated as right-censored for Kaplan–Meier analysis.

## Why this is more reproducible than the notebook
1. No hard-coded Windows path.
2. Every script can be rerun from the project root.
3. Raw rows are preserved.
4. Derived legal-delivery and all-row enriched files are saved separately.
5. Input SHA-256 is recorded.
6. Boolean parsing is explicit and does not incorrectly convert the string "FALSE" to True.
7. Analysis definitions are written in code.
8. Outputs are saved to stable folders.

## Run
Create a virtual environment, install:
`pip install -r requirements.txt`

Then:
`python src/07_run_all.py`

## Outputs
- `outputs/tables/data_validation_summary.csv`
- `outputs/tables/ball_by_ball_enriched_all_rows.csv`
- `outputs/tables/legal_deliveries_prepared.csv`
- `outputs/tables/innings_survival_dataset.csv`
- `outputs/tables/geometric_baseline_summary.csv`
- `outputs/tables/km_first_wicket_survival.csv`
- `outputs/tables/km_first_boundary_survival.csv`
- `outputs/tables/memoryless_comparison.csv`
- `outputs/tables/first_event_phase_summary.csv`
- `outputs/tables/phase_chi_square.csv`
- `outputs/figures/kaplan_meier_wicket_boundary.png`

## Reproducibility / publication note
The raw file remains the source of truth. Every filtering step creates a new derived object/file. Therefore, saying "legal deliveries were used" does not mean non-legal observations were deleted from the dataset.
