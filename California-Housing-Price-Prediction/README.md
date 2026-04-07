# California Housing Price Prediction 

This repository contains an end-to-end Machine Learning project focused on predicting median house values in California. The project follows the complete ML lifecycle: from data exploration and stratified sampling to building automated preprocessing pipelines and evaluating multiple regression models.

## Project Overview
The goal is to use various district-level features (population, median income, etc.) to predict the `median_house_value`. This project demonstrates how to handle real-world data challenges like missing values and categorical attributes.

## 🛠️ Tech Stack
- **Language:** Python
- **Libraries:** Pandas, NumPy, Scikit-Learn, Matplotlib
- **Tools:** Jupyter Notebooks, GitHub

## Repository Structure
- `data/`: The `housing.csv` dataset.
- `notebooks/`: Step-by-step exploration including EDA and Pipeline building.
- `src/`: Consolidated `main.py` script for training and evaluation.
- `docs/`: Includes the `sklearn HANDBOOK.pdf` used for methodology.

## Key Implementation Details
1. **Stratified Sampling:** Implemented `StratifiedShuffleSplit` based on income categories to ensure the test set is representative of the whole population.
2. **Automated Pipelines:** Created a `ColumnTransformer` to handle numerical scaling (`StandardScaler`) and categorical encoding (`OneHotEncoder`) in a single workflow.
3. **Model Evaluation:** Compared **Linear Regression**, **Decision Trees**, and **Random Forest** using 10-fold Cross-Validation.

## Results
The Random Forest Regressor provided the best results during training:
- **Linear Regression RMSE:** ~69,052
- **Decision Tree RMSE:** ~71,120
- **Random Forest RMSE:** ~50,182 (Best Performer)

## How to Run
1. Clone the repo:
   ```bash
   git clone [https://github.com/your-username/california-housing.git](https://github.com/your-username/california-housing.git)
