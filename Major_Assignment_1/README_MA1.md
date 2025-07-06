# Bulldozer Price Prediction

This project predicts the sale price of bulldozers and heavy machinery using historical auction data provided by Fast Iron.

## Project Files

- `Train.csv`, `Valid.csv`, `Test.csv`: Input datasets
- `TrainAndValid.csv`: Combined data for training
- `ValidSolution.csv`: Ground truth for validation
- `Bulldozer Price Prediction.ipynb`: Google Colab notebook with code
- `test_predictions.csv`: Final submission predictions
- `Data Dictionary.xlsx`: Feature descriptions
- `Machine Appendix.xlsx`: Equipment metadata
- `median_benchmark.csv`, `random_forest_benchmark_test.csv`: Benchmark files

## Evaluation Metric

- Root Mean Squared Logarithmic Error (RMSLE)

## Model

- Random Forest Regressor with basic preprocessing.
- Optionally compares against benchmark models.

## Approach
- Cleaned data: removed high-cardinality object columns, handled missing values.
- Used `RandomForestRegressor` to train on `Train.csv`.
- Evaluated using RMSLE on `Valid.csv` vs `ValidSolution.csv`.
- Final predictions saved in `test_predictions.csv`.

  



