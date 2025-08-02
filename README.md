# EV Adoption Forecasting for Washington State

This project provides an end-to-end solution for forecasting Electric Vehicle (EV) adoption at the county level in Washington State. It uses a machine learning model trained on historical vehicle registration data to predict future EV population trends, and it deploys this model into an interactive web application built with Streamlit.


## Project Overview

As electric vehicle adoption surges, urban planners face the critical challenge of anticipating infrastructure needs, especially for charging stations. Inadequate planning can lead to bottlenecks and hinder sustainability goals. This project addresses this problem by building a robust regression model that forecasts future EV adoption demand based on historical growth trends, vehicle types, and regional data.

The final output is an interactive dashboard where users can select a county and a future date to receive an instant EV population forecast.

## Key Features

*   **Time-Series Forecasting:** Predicts the total number of EVs for up to 36 months in the future.
*   **County-Level Analysis:** Provides granular forecasts for each county in Washington State.
*   **Interactive Dashboard:** A user-friendly web interface built with Streamlit for easy access to predictions.
*   **High-Accuracy Model:** Utilizes a Random Forest Regressor optimized for performance.

## Technology Stack

*   **Data Analysis & Manipulation:** `pandas`, `numpy`
*   **Machine Learning:** `scikit-learn`
*   **Data Visualization:** `matplotlib`, `seaborn`
*   **Web Application:** `streamlit`
*   **Model Persistence:** `joblib`
*   **Development Environment:** Python, Jupyter Notebook


## Setup and Installation

Follow these steps to set up and run the project locally:

1.  **Clone the Repository**
    ```
    git clone https://github.com/your-username/EV-Adoption-Forecasting.git
    cd EV-Adoption-Forecasting
    ```

2.  **Create and Activate a Virtual Environment** (Recommended)
    ```
    # For Windows
    python -m venv venv
    venv\Scripts\activate

    # For macOS/Linux
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Install the Required Packages**
    ```
    pip install -r requirements.txt
    ```

4.  **Run the Streamlit Application**
    ```
    streamlit run app.py
    ```
    Open your web browser and navigate to the local URL provided (usually `http://localhost:8501`).

## Methodology

The project follows a structured data science workflow:

1.  **Data Preparation:** The raw dataset was loaded, cleaned, and filtered for Washington State. Categorical features like `County` were encoded.
2.  **Feature Engineering:** Created time-series features like lags, rolling averages, and growth metrics to help the model learn historical patterns.
3.  **Model Development:** A `RandomForestRegressor` was chosen for its robustness and accuracy.
4.  **Model Optimization:** The model's hyperparameters were fine-tuned using `RandomizedSearchCV` to maximize predictive performance.
5.  **Evaluation:** The final model was rigorously evaluated on a test set using R-squared, MAE, and MSE metrics.
6.  **Deployment:** The trained model was saved using `joblib` and integrated into a `streamlit` web application.

## Model Performance

The final model demonstrated strong predictive power on the unseen test data:

*   **R-squared (R²) Score:** **0.979**
*   **Mean Absolute Error (MAE):** **1.49**

An R² score of 0.979 indicates that the model can explain approximately 98% of the variance in the EV population data, making it highly reliable for forecasting.

## Future Scope

*   **Advanced Modeling:** The forecasting accuracy could be further improved by experimenting with more specialized time-series algorithms like **SVR, Prophet, or LSTMs** to better capture non-linear trends.
*   **Enriched Data:** Future iterations could incorporate external datasets—such as **local economic indicators, historical gas prices, or data on government incentives**—to create an even more comprehensive forecasting model.


