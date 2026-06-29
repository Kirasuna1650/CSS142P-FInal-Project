# CSS142P Final Project

Monte Carlo simulation of player retention under alternative pity systems in an FGO-style gacha model.

## Project Contents

- `CSS142P-FinalProject.ipynb` - main notebook with the simulation, scenario comparison, visualization, and export steps
- `CSS142P-FinalProject.md` - project write-up draft
- `scenario_summary.csv` - scenario-level summary output
- `scenario_confidence_intervals.csv` - replication-based confidence interval output
- `scenario_sensitivity.csv` - sensitivity analysis output
- `Diagrams/` - exported PNG diagrams from the notebook

## Requirements

- Python 3.14 or compatible Python 3 version
- Jupyter Notebook or VS Code with the Jupyter extension
- Python packages: `numpy`, `pandas`, and `matplotlib`

The repository already includes a local virtual environment at `.venv`.

## Run Locally

### Option 1: VS Code

1. Open the folder `finalProj` in VS Code.
2. Open `CSS142P-FinalProject.ipynb`.
3. Select the `.venv` kernel if prompted.
4. Run the notebook cells from top to bottom.

### Option 2: Jupyter Notebook

```bash
cd "/Users/mamaril/Documents/School Projs/T32526/CSS142P/finalProj"
source .venv/bin/activate
jupyter notebook
```

Then open `CSS142P-FinalProject.ipynb` and run all cells in order.

## Rebuild Outputs

Running the notebook regenerates the analysis outputs directly in the project folder:

- `scenario_summary.csv`
- `scenario_confidence_intervals.csv`
- `scenario_sensitivity.csv`
- `Diagrams/acquisition_retention.png`

To refresh everything from scratch, run the notebook from the first cell through the final export cell.

## Notes

- The notebook uses synthetic player profiles and Monte Carlo simulation, so results may vary slightly if the random seeds or replication settings are changed.
- If you change the scenario parameters or simulation logic, rerun the entire notebook to update the CSV files and PNG diagram.