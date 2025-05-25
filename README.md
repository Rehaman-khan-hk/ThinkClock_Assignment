# ThinkClock Battery Labs Assignment

## Overview
This repository contains the submission for the **Python Developer Assignment** provided by **ThinkClock Battery Labs** (Web: [www.thinkclock.com](https://www.thinkclock.com), Email: [contact@thinkclock.com](mailto:contact@thinkclock.com)). The assignment involves analyzing the [NASA Battery Dataset](https://www.kaaale.com/datasets/patrickfleith/nasa-battery-dataset/data) to perform electrochemical impedance spectroscopy (EIS) visualization, incremental capacity analysis (ICA), and machine learning for battery capacity prediction.

The solutions are implemented in Python using Pandas, NumPy, Scikit-learn, and Matplotlib, executed in a Jupyter Notebook on an 8GB RAM system. The tasks address battery aging through repeated charge/discharge cycles, leveraging EIS measurements and charge cycle data.

**Note**: In completing this assignment, resources such as Google and AI tools may have been utilized to ensure a professional and thorough submission, supplementing personal expertise to meet high standards.

## Assignment Tasks
The assignment consists of three tasks:

1. **Task a: 3D EIS Plot**
   - **Objective**: Create a 3D plot of EIS measurements (Re(Z) vs. -Im(Z) vs. cycle count) at 24°C.
   - **Approach**: Filter `metadata.csv` for impedance tests, extract `Re`, set `-Im(Z)` to zero (missing in dataset), use `uid` as cycle count. Generate a 3D scatter plot.
   - **Output**: `eis_3d_plot.png`, `eis_3d_plot.pdf`.

2. **Task b: 3D ICA Plot**
   - **Objective**: Derive incremental capacity (dQ/dV) from charge cycles and create a 3D plot (dQ/dV vs. voltage vs. cycle count).
   - **Approach**: Compute capacity (\( Q = \int I \, dt \)) and dQ/dV from charge cycle files, filter valid data, and plot voltage vs. dQ/dV vs. cycle count.
   - **Output**: `ica_3d_plot.png`, `ica_3d_plot.pdf`.

3. **Task c: Machine Learning Model for Capacity Prediction**
   - **Objective**: Train a model to predict battery capacity from EIS signatures (Re, Rct).
   - **Approach**: Use Gradient Boosting Regressor with features `Re`, `Rct`, `Re+Rct`, compute capacity from charge cycles, evaluate with Mean Absolute Error (MAE: 0.0423 Ah).
   - **Output**: `predictions_plot.png`, `predictions_plot.pdf`, `capacity_predictor.pkl`, `capacity_scaler.pkl`, `model_performance.csv`.

## Repository Contents
- **ThinkClock_Assignment.ipynb**: Jupyter Notebook containing all code (data exploration, Q3a, Q3b, Q3c) and plot visualizations.
- **submission.pdf**: Compiled LaTeX document detailing methodology, plots, and results.
- **eis_3d_plot.png**, **eis_3d_plot.pdf**: 3D EIS plot for Battery B0005.
- **ica_3d_plot.png**, **ica_3d_plot.pdf**: 3D ICA plot for Battery B0005.
- **predictions_plot.png**, **predictions_plot.pdf**: Predicted vs. actual capacity plot for Q3c.
- **capacity_predictor.pkl**: Trained Gradient Boosting model.
- **capacity_scaler.pkl**: Feature scaler for Q3c.
- **model_performance.csv**: Model metrics (MAE, RMSE, R2, CV MAE) for Q3c.
- **README.md**: This file.

**Note**: The dataset (`metadata.csv` and `data/` directory) is not included due to size constraints. Download it from [Kaggle](https://www.kaaale.com/datasets/patrickfleith/nasa-battery-dataset/data) and place it in `NASA_BATTERY_dataset/cleaned_dataset/` relative to the notebook.

## Prerequisites
- **Python Version**: 3.8 or higher
- **Dependencies**:
  ```bash
  pip install pandas numpy scikit-learn matplotlib joblib scipy
