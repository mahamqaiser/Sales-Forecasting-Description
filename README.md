# Sales Forecasting with XGBoost

This project predicts **weekly sales** for retail stores using historical sales, store details, and additional features. It leverages **XGBoost Regression** for accurate time series forecasting with lag features, time-based variables, and store-specific data.

## Requirements
- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- xgboost

Install dependencies with:
pip install pandas numpy matplotlib seaborn scikit-learn xgboost

## Dataset
The project uses three CSV files:
- **train.csv**: Historical weekly sales per store and department.
- **stores.csv**: Store-level metadata (e.g., type, size).
- **features.csv**: Additional information such as holidays, temperature, fuel price, CPI, and unemployment.

Make sure the file paths in the script are updated to your dataset location:

## Workflow
1. **Data Merging**: Combines training, store, and feature datasets.
2. **Date Processing**: Converts `Date` to datetime and extracts `Year`, `Month`, `Week`, and `Day`.
3. **Lag Feature Creation**: Adds 1-week and 2-week lagged sales for each store and department.
4. **Data Cleaning**: Fills missing lag values and encodes categorical features (`IsHoliday` and `Type`).
5. **Feature/Target Split**: Defines predictors (X) and target (`Weekly_Sales`).
6. **TimeSeriesSplit**: Ensures chronological splitting for training and testing.
7. **Model Training**: Fits an `XGBRegressor` with specified hyperparameters.
8. **Prediction & Evaluation**: Predicts sales and calculates **Root Mean Squared Error (RMSE)**.
9. **Visualization**: Plots actual vs predicted sales for the test set.

## Running the Project
1. Place all CSV files in the correct directory or update paths in the script.
2. Install the dependencies listed above.
3. Run the script:
   python sales_forecasting.py

## Notes
- Lag features help capture weekly seasonality trends.
- Model performance can be improved by tuning XGBoost parameters or adding more domain-specific features.
- Ensure the datasets have consistent column names and formats before running.

## License
This project is open-source and free for educational and research purposes.

