# Machine-Learning-Analysis-of-Pore-Structure-CO2-Adsorption-Relationships-in-Activated-Carbons
Machine learning codes for analyzing pore structure–CO2 adsorption relationships in activated carbons using raw and normalized pore size distribution features.
# Machine Learning Analysis of Pore Structure–CO2 Adsorption Relationships in Activated Carbons

This repository provides machine learning codes used to analyze the structure–property relationships between pore structure and CO2 adsorption performance in activated carbons.

The codes were developed as part of a data-driven study on activated-carbon CO2 adsorption, in which pore-structure parameters and pore size distribution (PSD) features were used to predict adsorption capacity and identify key effective pore ranges.

## Repository contents

This repository includes six machine learning scripts based on three models:

- XGBoost (XGB)
- Random Forest (RF)
- Multilayer Perceptron (MLP)

Each model is provided in two feature versions:

### 1. Raw pore size distribution features
- `XGB_PSD.py`
- `RF_PSD.py`
- `MLP_PSD.py`

These scripts use raw pore size distribution features together with conventional pore-structure descriptors.

### 2. Normalized pore size distribution features
- `XGB_PSD_VMI.py`
- `RF_PSD_VMI.py`
- `MLP_PSD_VMI.py`

These scripts use normalized pore size distribution features, where each PSD interval is divided by micropore volume (VMI), together with pore-structure descriptors.

## Research background

Activated carbon is one of the most important adsorbents for CO2 capture. However, the relationship between pore structure and adsorption performance is highly nonlinear and cannot be adequately described by a single structural parameter such as specific surface area or total pore volume.

To address this problem, this study combines machine learning with pore-structure feature engineering to identify the pore characteristics most relevant to CO2 adsorption. In particular, the repository compares two feature strategies:

- direct use of raw pore size distribution features;
- use of normalized PSD/VMI features to better reflect the relative contribution of different pore ranges.

## Input features

Depending on the script, the model inputs may include:

- `SBET` — specific surface area
- `VT` — total pore volume
- `VMI` — micropore volume
- `T` — adsorption temperature
- `P` — adsorption pressure
- pore size distribution interval features (e.g., `0.3_0.4`, `0.5_0.6`, `0.6_0.7`, etc.)
- `Micropore_Ratio` (`VMI/VT`)

For the normalized-feature scripts, PSD interval features are transformed as:

PSD/VMI = (pore volume in a given pore-size interval) / VMI

## Target variable

- `CO2` — CO2 adsorption capacity

## Model outputs

The scripts are mainly used to generate model-performance data for plotting and comparison.  
Typical outputs include:

- train/test prediction results
- parity plot data
- cross-validation performance data
- summary metrics such as:
  - R2
  - RMSE
  - MAE
- fitted line parameters for parity plots

Some scripts may also export CSV files for subsequent visualization in Origin or other plotting software.

## Purpose of this repository

This repository is intended to:

- share the machine learning codes used in the study;
- support transparency and reproducibility of the modeling workflow;
- facilitate comparison between raw PSD and normalized PSD/VMI feature strategies;
- provide methodological reference for future studies on porous carbon adsorbents.

## Notes

- These scripts are shared primarily for methodological reference.
- Input data files are not included in this repository unless separately stated.
- Some file paths in the scripts may be local absolute paths and should be modified by users according to their own computing environment.
- Users should prepare their own datasets with matching column names before running the scripts.

## Recommended file naming

To keep the repository clear and consistent, the following naming convention is recommended:

- `XGB_PSD.py`
- `RF_PSD.py`
- `MLP_PSD.py`
- `XGB_PSD_VMI.py`
- `RF_PSD_VMI.py`
- `MLP_PSD_VMI.py`

## Citation

If you use these codes or find them helpful, please cite the associated study when available.

## Disclaimer

This repository contains research code for academic use.  
Users are responsible for verifying data quality, adapting file paths, and ensuring that the scripts are used appropriately in their own computational environment.
