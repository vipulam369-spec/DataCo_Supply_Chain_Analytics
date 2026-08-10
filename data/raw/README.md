# Raw Dataset

This directory contains the original source dataset used to establish the project's analytical audit trail.

## Source

DataCo SMART SUPPLY CHAIN FOR BIG DATA ANALYSIS

Kaggle:
https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis

Source file:

`DataCoSupplyChainDataset.csv`

## Local project filename

For the project workflow, the source dataset is loaded as:

`Raw_DataCoSupplyChainDataset.csv`

If the downloaded Kaggle file is named `DataCoSupplyChainDataset.csv`, rename it to `Raw_DataCoSupplyChainDataset.csv` before running the notebook.

## Repository note

The raw CSV is not committed to this repository because of its file size.

The notebook loads the raw dataset first, performs the documented audit and cleaning workflow, and produces the cleaned analytical dataset used by the downstream project artifacts.

## Local setup

1. Download the source dataset from Kaggle.
2. Rename the downloaded file to `Raw_DataCoSupplyChainDataset.csv`.
3. Place it in this directory.
4. Run the final analytics and ML notebook from the project environment.
