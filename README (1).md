# DWSIM Process Optimization

> Process flowsheet simulated in DWSIM, with parameter trials analysed in Python to find the best-performing operating settings.

## Overview
A simple process flowsheet was built in **DWSIM** and run through trials that vary key operating parameters. The effect of each change on **efficiency** and **output** was recorded, and the best-performing settings were identified.

## Workflow
1. Build the flowsheet in DWSIM (add your `.dwxmz` file under `simulation/`).
2. Vary one operating parameter at a time (e.g. feed temperature, pressure, reflux ratio).
3. Record efficiency and output for each trial in `data/dwsim_trials.csv`.
4. Run the notebook to plot effects, rank trials and pick the best settings.

## What the notebook does
- Plots each parameter against efficiency and output
- Computes slope and correlation for every parameter-response pair
- Finds best-efficiency, best-output and best-balanced trials
- Shows the efficiency vs output trade-off

## Project structure
```
dwsim-process-optimization/
├── dwsim_trial_analysis.ipynb
├── simulation/            # your DWSIM flowsheet file (.dwxmz) and screenshots
├── data/                  # dwsim_trials.csv
├── requirements.txt
└── README.md
```

## Data format
`data/dwsim_trials.csv`
| trial | feed_temp_C | pressure_kPa | reflux_ratio | efficiency_pct | output_kg_h |
|---|---|---|---|---|---|
Edit `PARAMS` / `RESPONSES` in the notebook to match your flowsheet. Without the file, the notebook runs on **synthetic demo data** (clearly labelled).

## Getting started
```bash
pip install -r requirements.txt
jupyter notebook dwsim_trial_analysis.ipynb
```
Install DWSIM (free, open source) from https://dwsim.org to run the simulation itself.

## Results
Add your real findings here: best settings, efficiency/output achieved, and a flowsheet screenshot.

## Tech stack
DWSIM, Python (pandas, NumPy, Matplotlib), Jupyter

## Author
Rohini Datkar
