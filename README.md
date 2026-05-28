# ACDI Weight Optimization for Agricultural Cold Damage

This repository provides the Python code used for the data-driven weight optimization of the Agricultural Cold Damage Index (ACDI). The code was developed to support the manuscript:

**Optimizing a Satellite-based Agricultural Cold Damage Index through Thermo-Hydrological Factor Weighting**

## Overview

The script extends the conventional equal-weight ACDI framework by assigning optimized weights to four thermo-hydrological factors:

- F1: Cold intensity
- F2: Rapid cooling
- F3: Thermal imbalance
- F4: Cold–dry interaction

The weighted ACDI is calculated as:

ACDIw = w1 × Z(F1) + w2 × Z(F2) + w3 × Z(F3) + w4 × Z(F4)

where the weights satisfy:

w1 + w2 + w3 + w4 = 1

The code performs:

1. One-factor-at-a-time sensitivity analysis
2. Response surface analysis for selected weight combinations
3. Pareto-based multi-objective optimization
4. Comparison between equal-weight and optimized-weight ACDI time series
5. Generation of manuscript-style figures

## Input Data

The code requires event-based CSV files generated from NASA SMAP Level 4 soil moisture and temperature data.

Expected file pattern:

event_*_SMAP_L4_SPL4SMGP*_30d_to_3d_4perday_sm_temp_layers.csv

Required columns include:

datetime_kst
event_time_kst
sm_surface
sm_rootzone
surface_temp
soil_temp_layer1
soil_temp_layer2

Additional soil temperature layers may also be included.

## Main Script

weightfactor.py

Before running the script, update the following path in the user settings section:

SMAP_DIR = Path("path/to/your/SMAP/event/csv/files")

## Outputs

The script creates an output folder named:

acdi_weight_optimization

The following result files are generated:

weight_grid.csv
weight_grid_event_metrics.csv
weight_grid_mean_metrics.csv
selected_optimized_weight.csv
pareto_optimal_weights.csv
sensitivity_analysis_results.csv
response_surface_w3_w4.csv

The following figure files are also generated:

Figure_1_sensitivity_analysis.png
Figure_2_response_surface.png
Figure_3_pareto_and_optimized_timeseries.png

## Requirements

The code was written in Python and requires the following packages:

numpy
pandas
matplotlib

These packages can be installed using:

pip install numpy pandas matplotlib


## Citation

If this code is used, please cite the associated manuscript and the archived Zenodo DOI for this repository.

## License

This repository is provided for academic and research purposes. Users may modify and reuse the code with appropriate citation.
