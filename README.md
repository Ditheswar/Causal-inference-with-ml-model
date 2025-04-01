# Retail Pricing Optimization System

## Project Description

This project develops a data-driven system for optimizing retail pricing strategies. It addresses the limitations of traditional pricing approaches by integrating causal inference and predictive modeling to provide dynamic and informed pricing recommendations. The system aims to enhance pricing decisions by:

* **Estimating Causal Effects:** Quantifying the true impact of price on sales, mitigating the risks associated with relying solely on correlational analyses.
* **Forecasting Demand:** Employing predictive modeling to forecast sales trends and anticipate future demand patterns.
* **Recommending Optimal Pricing:** Generating data-driven pricing recommendations that optimize key business objectives.

## Methodology

The system's methodology comprises the following stages:

1.  **Data Acquisition and Preprocessing:**
    * Ingestion of retail data from CSV files.
    * Data cleansing, transformation, and feature engineering, including the calculation of a final price metric.
    * Encoding of categorical variables using one-hot encoding.
    * Scaling of numerical features to ensure model stability and performance.

2.  **Causal Inference Modeling:**
    * Specification of a causal graph to represent hypothesized relationships between relevant variables.
    * Implementation of causal inference using the `DoWhy` library to:
        * Identify estimable causal effects of price on sales.
        * Estimate the magnitude of these effects.
        * Conduct refutation analyses to assess the robustness of causal effect estimates.

3.  **Predictive Modeling with Bayesian Networks:**
    * Construction of a Bayesian Network model using the `pgmpy` library to:
        * Learn the network structure from the preprocessed data.
        * Train the model parameters.
        * Perform probabilistic inference to predict sales volumes.

4.  **Pricing Recommendation Engine:**
    * Integration of causal effect estimates and sales predictions to generate optimal pricing recommendations.

5.  **Evaluation and Visualization:**
    * Evaluation of the Bayesian Network model's predictive performance using relevant metrics (e.g., R-squared, MAE, RMSE).
    * Visualization of causal effect estimates and model predictions to facilitate interpretation.

6.  **Interactive Scenario Analysis:**
    * Provision for user-defined input to simulate pricing scenarios.
    * Generation of adjusted pricing recommendations based on user-specified parameters.

## Code Description

The system is implemented in Python and leverages the following libraries:

* `pandas`: Data manipulation and analysis.
* `numpy`: Numerical computing.
* `matplotlib.pyplot`: Data visualization.
* `seaborn`: Enhanced data visualization.
* `DoWhy`: Causal inference framework.
* `networkx`: Graph manipulation.
* `statsmodels.api`: Statistical modeling.
* `sklearn.metrics`: Model evaluation metrics.
* `pgmpy`: Probabilistic graphical modeling.
* `sklearn.preprocessing`: Data preprocessing.

The core functionalities of the code include:

1.  **Data Loading and Preprocessing:**
    * Reading data from CSV files.
    * Calculating final prices after discounts.
    * Removing irrelevant columns.
    * Encoding categorical variables.
    * Scaling numerical features.

2.  **Causal Inference:**
    * Defining the causal graph structure.
    * Constructing a causal model using `DoWhy`.
    * Identifying and estimating the causal effect of price on sales.
    * Performing refutation tests to validate causal estimates.

3.  **Bayesian Network Modeling:**
    * Learning the Bayesian Network structure.
    * Training the Bayesian Network model.
    * Predicting sales based on relevant factors.

4.  **Evaluation and Output:**
    * Calculating model performance metrics.
    * Generating visualizations.
    * Providing optimal pricing recommendations.
    * Enabling user-driven scenario analysis.

## Objectives

This project is designed to achieve the following objectives:

* **Causal Effect Estimation:** To accurately estimate the causal impact of price on sales using the `DoWhy` library.
* **Demand Forecasting:** To predict sales volumes based on relevant factors, including competitor pricing, using a Bayesian Network model.
* **Dynamic Pricing Recommendation:** To generate adjusted price recommendations based on estimated causal effects and Bayesian Network predictions.
* **Causal Inference Validation:** To perform refutation tests to assess the robustness and reliability of causal effect estimates.
* **Predictive Model Evaluation:** To evaluate the predictive performance of the Bayesian Network model using appropriate metrics (e.g., R-squared, MAE, RMSE).
* **Data Visualization:** To visualize causal effect estimates and predicted sales to facilitate interpretation and communication of results.
* **Interactive Scenario Analysis:** To enable users to explore different pricing scenarios and obtain adjusted price recommendations through user-defined inputs.

## Usage

1.  **Installation:**

    ```bash
    !pip install dowhy networkx
    ```

    Install the required Python libraries.

2.  **Data Preparation:**

    * Ensure that your retail data is structured in a CSV file.
    * Modify the file path within the code to point to your data source.

3.  **Code Execution:**

    * Execute the Python script.
    * The script will perform the following operations:
        * Causal inference analysis.
        * Bayesian Network modeling and prediction.
        * Generation of pricing recommendations.
    * The script will prompt you to enter test values for interactive pricing scenario analysis.

## Important Considerations

* **Prediction Accuracy:** The provided code snippet requires correction in the predicted sales calculation for accurate performance evaluation.
* **Pricing Strategy:** The current implementation employs a simplified linear adjustment for optimal pricing. Advanced pricing strategies may yield improved results.
* **Causal Graph Specification:** The causal graph is currently hardcoded. Consider implementing a more flexible approach for graph specification and ensure thorough documentation of the chosen causal relationships.
