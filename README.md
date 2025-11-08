# banff-ev-modelling

**Agent-based Monte Carlo model of electric vehicle (EV) charging demand for the Town of Banff, Alberta.**  
This repository contains the simulation framework, analysis scripts, and scenario results used in the MSc thesis by **Grayden Wiebe** (University of Alberta, Department of Mechanical Engineering).

---

## Overview

As electric vehicle adoption accelerates, tourism-driven municipalities face unique charging infrastructure challenges.  
This project models and evaluates Banff’s EV charging system using an **agent-based Monte Carlo simulation**, integrating:

- **Empirical traffic and visitor data** (2013–2025)
- **Probabilistic EV arrival, SOC, and charging behavior**
- **Temperature-dependent charging performance**
- **Public/private accessibility ratios and utilization metrics**

The framework produces hourly system-level performance indicators:
- Charger utilization rates  
- Waiting times and queue lengths  
- Energy delivered and EVs charged successfully  
- Sensitivity of infrastructure adequacy under growth scenarios

---

## Requirements

Python ≥ **3.10**
Jupyter package

Core libraries:\
% ```bash\
% pip install numpy pandas matplotlib scipy tqdm joblib requests scikit-learn\



## Running the Simulation

Download the `EVLoadProfile_10.6.2.ipynb` file.
Download "soc_distribution.pkl" to the same folder.

All simulations are run through `EVLoadProfile_10.6.2.ipynb`

Each script automatically fetches the relevant datasets from GitHub (traffic counts, temperature reductions).

## Model Highlights

Monte Carlo Sampling: Generates probabilistic EV arrivals, charging durations, and SOCs.

Agent-Based Queueing: Simulates each EV's wait, charge, or leave behavior.

Temperature Derating: Applies thermal reductions to charging power based on ambient temperature.

Infrastructure Scenarios: Configurable charger counts, accessibility ratios, and expansion strategies.

## Outputs

Each run exports:

- Time-series of total and average power demand (avg_total_power.csv)
- EV-level results (ev_data_df.jsonl)
- Scenario metrics (scenario_metrics.pkl)

Optional plots:

- Daily load profiles
- Power histograms
- Queue and waiting time distributions

## Key Files
File	Purpose
ev_model_core.py	Core simulation engine and agent logic
baseline_simulation.py	Reproduces Banff’s 2024 baseline system
monte_carlo_convergence.py	Validates simulation stability
ev_penetration_analysis.py	Simulates growth in EV adoption
scenario_simulations.py	Multi-factor scenario analysis
scenario_significance_analysis.py	Factorial significance testing
ev_extras_unnecessary.py	Helper functions and visualization tools

## Citation

If you use this model or its results in your work, please cite:

Wiebe, G. (2025). Electric Vehicle Charging Load Modeling in Touristic Towns: A Case Study of Banff, Alberta.
MSc Thesis, University of Alberta, Department of Mechanical Engineering.

## Author

Grayden Wiebe, E.I.T.
MSc Candidate – Mechanical Engineering, University of Alberta
Email: gewiebe@ualberta.ca

## License

This project is licensed under the **Apache License 2.0**.  
You are free to use, modify, and distribute this code for academic or commercial purposes, provided that proper attribution is given.

## Acknowledgments

This research was supported by Future Energy Systems (FES) at the University of Alberta.

Special thanks to Dr. Pierre Mertiny (Supervisor).
