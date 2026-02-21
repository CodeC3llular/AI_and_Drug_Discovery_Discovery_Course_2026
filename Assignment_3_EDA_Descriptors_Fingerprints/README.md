# Assignment 3: Exploratory Data Analysis & Descriptor/Fingerprint Calculation

## Overview
This folder contains all files for Assignment 3 of the AI and Drug Discovery Course.

## Target Protein
EGFR (Epidermal Growth Factor Receptor)

## Dataset
- 66 molecules from ChEMBL database
- Features: SMILES, pIC50 values, bioactivity class (active/inactive)

## Notebooks
- `QSAR_Part_2_Exploratory_Data_Analysis.ipynb` - Exploratory Data Analysis & Lipinski Descriptors
- `QSAR_Part_3_Pubchem_Fingerprint_Calculation.ipynb` - PaDEL Descriptors & Fingerprint Calculation

## Files
- `df_lipinski.csv` - Lipinski descriptors
- `pubchem_fingerprints.csv` - PubChem fingerprints (881 bits)
- `Substructure_fingerprints.csv` - Substructure fingerprints
- `QSAR_dataset.csv` - Combined ML-ready dataset
- `mannwhitney_summary.csv` - Mann-Whitney U test results

## Tools Used
- RDKit - Lipinski descriptor calculation
- PaDELpy - 2D descriptors & fingerprint calculation

## Author
Michelle Mupanduki
