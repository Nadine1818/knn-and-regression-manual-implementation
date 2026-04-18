# ML Notebooks: KNN Classification + Regression

This repository contains two Jupyter notebooks:

- **KNN Classification**: K-Nearest Neighbors classification on the MAGIC Gamma Telescope dataset.
- **Regression**: Regression models (Linear/Ridge/Lasso/Polynomial) on the California Housing dataset.

## Project structure

- `Knn_classification.ipynb` — KNN classification notebook
- `regression.ipynb` — regression notebook
- `Knn_classification.pdf`, `regression.pdf` — exported notebook reports
- `telescope_data/` — expected location for telescope dataset CSV
- `California_Houses/` — expected location for California housing dataset CSV

## Datasets

This repo is configured to **not commit `.csv` files** (useful for public repos).

To run the notebooks, place the CSV files here:

- `telescope_data/telescope_data.csv`
- `California_Houses/California_Houses.csv`

## Run locally

1. Create/activate a Python environment.
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Start Jupyter and open the notebooks:

   ```bash
   jupyter notebook
   ```

## Requirements

See `requirements.txt`.
