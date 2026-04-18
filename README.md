# ML Notebooks: KNN Classification + Regression

This folder contains two Jupyter notebooks covering:

- **KNN Classification** on the MAGIC Gamma Telescope dataset.
- **Regression** experiments on the California Housing dataset.

The goal is to compare **manual implementations** vs. **scikit-learn** baselines, and to report model performance using standard metrics.

## Project structure

- `Knn_classification.ipynb` — KNN classification notebook
- `regression.ipynb` — regression notebook
- `Knn_classification.pdf`, `regression.pdf` — exported notebook reports
- `telescope_data/` — expected location for telescope dataset CSV
- `California_Houses/` — expected location for California housing dataset CSV

## Datasets

This repo is configured to **not commit `.csv` files**.

To run the notebooks, place the CSV files here:

- `telescope_data/telescope_data.csv`
- `California_Houses/California_Houses.csv`

## Environment setup

1. Create/activate a Python environment.
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Launch Jupyter:

   ```bash
   jupyter notebook
   ```

## Notebook 1: KNN classification (MAGIC Gamma Telescope)

What’s covered:

- Basic dataset loading + preprocessing.
- **Manual KNN** (distance computation + neighbor voting).
- **scikit-learn KNN** baseline.
- Hyperparameter sweep over $k$ values and selection based on validation accuracy.
- Metrics reported: **Accuracy, Precision, Recall, F1 Score**.

### Results summary (validation set)

Manual KNN (printed notebook outputs):

| k | Accuracy | Precision | Recall | F1 Score |
|---:|:--------|:----------|:-------|:---------|
| 1  | 0.7841  | 0.7612    | 0.8273 | 0.7929   |
| 3  | 0.8021  | 0.7661    | 0.8693 | 0.8144   |
| 7  | 0.8131  | 0.7738    | 0.8842 | 0.8253   |
| 11 | 0.8136  | 0.7745    | 0.8842 | 0.8257   |
| 15 | 0.8101  | 0.7674    | 0.8892 | 0.8239   |

Best-$k$ selection (printed notebook output):

- **Best k (Manual KNN): 11 with accuracy 0.8136**

scikit-learn KNN (validation accuracy printed in notebook outputs):

| k | Validation accuracy |
|---:|:-------------------|
| 1  | 0.784147557328016  |
| 3  | 0.8020937188434696 |
| 7  | 0.8130608175473579 |
| 11 | 0.8135593220338984 |
| 15 | 0.8100697906281157 |

## Notebook 2: Regression (California Housing)

What’s covered:

- Train/validation/test split and feature scaling.
- **Linear Regression** implemented using:
  - Normal Equation (closed-form)
  - Gradient Descent
  - scikit-learn baseline
- **Ridge Regression** (manual + Gradient Descent + scikit-learn), including a sweep over $\lambda$.
- **Lasso Regression** (manual + scikit-learn), including a sweep over $\lambda$.
- Metrics reported: **MSE** and **MAE** on train/validation/test.

### Results summary (printed notebook outputs)

Linear Regression:

| Method | Train MSE | Val MSE | Test MSE | Train MAE | Val MAE | Test MAE |
|:--|--:|--:|--:|--:|--:|--:|
| Normal Equation | 4730358742.50 | 4907211997.37 | 4400953150.61 | 49927.00 | 50790.06 | 48782.03 |
| Gradient Descent | 4730408123.01 | 4907251335.58 | 4400381466.22 | 49930.54 | 50793.08 | 48784.01 |
| Sklearn Linear Regression | 4730358742.50 | 4907211997.37 | 4400953150.61 | 49927.00 | 50790.06 | 48782.03 |

Ridge Regression:

| Method | Training MSE | Validation MSE | Test MSE | Training MAE | Validation MAE | Test MAE |
|:--|--:|--:|--:|--:|--:|--:|
| Manual (Normal) | 4730358742.53 | 4907212034.98 | 4400952696.86 | 49927.01 | 50790.06 | 48782.03 |
| Manual (Gradient Descent) | 4730536293.94 | 4907451682.70 | 4399970799.27 | 49935.62 | 50797.84 | 48787.70 |
| Sklearn Ridge | 4730358742.53 | 4907212034.98 | 4400952696.86 | 49927.01 | 50790.06 | 48782.03 |

Lasso Regression:

| Method | Training MSE | Validation MSE | Test MSE | Training MAE | Validation MAE | Test MAE |
|:--|--:|--:|--:|--:|--:|--:|
| Manual (Normal) | 5110333927.07 | 5332683448.11 | 4817466183.58 | 52684.59 | 53522.56 | 51650.02 |
| Sklearn Lasso | 4730361131.00 | 4907208018.68 | 4400731898.96 | 49927.07 | 50790.11 | 48781.67 |

## Notes on reproducibility

- Results in the summary tables above are taken from the notebooks’ printed outputs.
- If you re-run with different random splits or preprocessing choices, metrics may change.

## Requirements

See `requirements.txt`.
