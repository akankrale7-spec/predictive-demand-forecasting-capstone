# Predictive Demand Forecasting Using Data Science

## Project Overview

This Data Science Capstone Project focuses on forecasting future product demand using historical daily demand data. The project applies statistical and machine learning techniques to identify demand patterns and generate accurate predictions.

## Research Question

**How accurately can historical demand patterns be used to forecast future daily demand?**

## Objectives

* Clean and prepare historical demand data.
* Explore trends and patterns in daily demand.
* Perform time-series analysis and stationarity testing.
* Develop predictive forecasting models.
* Compare model performance using standard evaluation metrics.
* Identify the best-performing model.
* Understand how demand forecasting can support business decisions.

## Dataset

The dataset contains daily demand observations along with additional information related to marketing events and holidays.

### Main Variables

* `date` – Date of observation
* `demand` – Daily demand
* `marketing_event` – Indicates whether a marketing event occurred
* `holiday` – Indicates whether the day was a holiday

## Methodology

The project follows the following workflow:

**Data Collection → Data Cleaning → Exploratory Data Analysis → Feature Engineering → Train/Test Split → Predictive Modeling → Model Evaluation → Business Insights**

### Data Preprocessing

* Converted dates into the appropriate datetime format.
* Sorted observations chronologically.
* Checked for missing values and duplicate records.
* Created lag and rolling-average features.

### Models Used

1. **Previous-Day Baseline**
2. **ARIMA (1,1,1)**
3. **Random Forest Regression**

## Feature Engineering

The following features were created:

* Previous-day demand (`lag1`)
* Seven-day lag demand (`lag7`)
* Seven-day rolling average (`rolling7`)
* Marketing event
* Holiday indicator

## Model Evaluation

Models are evaluated using:

* **MAE – Mean Absolute Error**
* **RMSE – Root Mean Squared Error**
* **MAPE – Mean Absolute Percentage Error**

The final observations are kept as an unseen chronological test set to evaluate out-of-sample forecasting performance.

## Results

The models are compared based on their prediction errors. On the provided dataset, the **Random Forest model achieved the lowest forecasting error** among the evaluated models.

| Model                 |      MAE |     RMSE |      MAPE |
| --------------------- | -------: | -------: | --------: |
| Previous-Day Baseline |     9.71 |    11.21 |     6.24% |
| ARIMA (1,1,1)         |    11.58 |    15.76 |     7.13% |
| Random Forest         | **2.99** | **4.28** | **1.87%** |

## Business Implications

Accurate demand forecasting can help organizations:

* Improve inventory planning.
* Reduce stockouts and excess inventory.
* Plan procurement more effectively.
* Allocate operational resources.
* Improve supply-chain decision making.
* Anticipate changes in customer demand.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Statsmodels
* Jupyter Notebook

## Repository Structure

```text
predictive-demand-forecasting-capstone/
│
├── data/
│   └── daily-demand-series.csv
│
├── demand_forecasting.ipynb
├── requirements.txt
├── README.md
└── Data_Science_Capstone_Demand_Forecasting_Presentation.pptx
```

## How to Run

1. Clone or download this repository.
2. Install the required Python libraries:

```bash
pip install -r requirements.txt
```

3. Open `demand_forecasting.ipynb` in Jupyter Notebook or VS Code.
4. Make sure `daily-demand-series.csv` is inside the `data` folder.
5. Run the notebook cells sequentially.

## Limitations

* The dataset is relatively small.
* A larger historical dataset would provide more reliable forecasting.
* Additional variables such as price, promotions, weather, and product category could improve predictions.
* More advanced time-series validation could be used for production deployment.

## Future Scope

Future improvements may include:

* SARIMA and other advanced forecasting models.
* Gradient boosting models.
* Longer historical datasets.
* Rolling time-series cross-validation.
* Forecast confidence intervals.
* Integration with real-time business data.
* Deployment as an interactive forecasting dashboard.

## Conclusion

This project demonstrates an end-to-end Data Science predictive modeling workflow, from data preprocessing and exploratory analysis to model development and evaluation. Among the tested models, Random Forest provided the best performance on the selected holdout period. The approach can support data-driven demand planning and supply-chain decision making.

## Project Deliverables

* Jupyter Notebook containing the complete implementation.
* Historical demand dataset.
* Model evaluation results.
* Data Science Capstone presentation.
* Formal research report / whitepaper.
