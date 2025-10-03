Multiple Linear Regression for Pulse Prediction

This project demonstrates a multiple linear regression model implemented in Google Colab to predict pulse rates using the `exercise` dataset from the `seaborn` library.

## Project Description

The goal of this project is to build a multiple linear regression model that can predict a person's pulse based on various exercise-related factors. The model utilizes one-hot encoding for categorical features and then trains a linear regression model to establish the relationship between these features and the pulse.

## Setup and Installation

This project is designed to run in Google Colab, which provides a pre-configured environment with all necessary libraries. No specific installation steps are required outside of running the Colab notebook.

## Dataset

The model uses the `exercise` dataset from the `seaborn` library. This dataset contains information about various exercise activities and their impact on physiological measures, including pulse.

**Features Used for Prediction (X):**

*   `id`: Identifier for the participant.
*   `diet`: Type of diet (e.g., "no fat", "low fat").
*   `time`: Time of exercise (e.g., "15 min", "30 min").
*   `kind`: Type of exercise (e.g., "rest", "walking", "running").

**Target Variable (Y):**

*   `pulse`: The pulse rate of the participant.

## Code Overview

The provided Python code performs the following steps:

1.  **Import Libraries:** Imports necessary libraries: `seaborn` for data loading, `ColumnTransformer` and `OneHotEncoder` from `sklearn.compose` and `sklearn.preprocessing` for categorical feature encoding, `numpy` for numerical operations, `train_test_split` from `sklearn.model_selection` for data splitting, and `LinearRegression` from `sklearn.linear_model` for the regression model.
2.  **Load Dataset:** Loads the `exercise` dataset using `sns.load_dataset('exercise')`.
3.  **Define Features and Target:** Separates the dataset into features (X) and the target variable (Y).
4.  **One-Hot Encoding:**
    *   Identifies categorical features: `diet`, `time`, and `kind`.
    *   Uses `ColumnTransformer` with `OneHotEncoder` to transform these categorical features into a numerical format. This creates new binary columns for each category, preventing the model from assuming ordinal relationships.
5.  **Split Data:** Divides the dataset into training and testing sets using `train_test_split` with a `test_size` of 20% and a `random_state` of 0 for reproducibility.
6.  **Train Model:** Initializes and trains a `LinearRegression` model using the training data (`X_train`, `Y_train`).
7.  **Make Predictions:** Generates predictions on the test set (`X_test`) using the trained model.
8.  **Evaluate Predictions:** Prints a concatenated array showing the predicted pulse values (`y_pred`) alongside the actual pulse values from the test set (`Y_test`) for comparison. `np.set_printoptions(precision = 2)` is used to format the output for better readability.

## How to Run

1.  Open Google Colab (colab.research.google.com).
2.  Create a new Python 3 notebook.
3.  Copy and paste the entire code block provided in the project description into a code cell.
4.  Run the cell by clicking the "Play" button or pressing `Shift + Enter`.

The output will display the predicted pulse values alongside the actual pulse values from the test set.

## Example Output

The output will be a two-column array. The first column will contain the predicted pulse values, and the second column will contain the actual pulse values from the test set.

```text
[[97.77 90.  ]
 [91.75 90.  ]
 [91.43 96.  ]
 [91.07 90.  ]
 [90.58 90.  ]
 [92.01 90.  ]
 [90.96 90.  ]
 [90.68 90.  ]
 [90.31 88.  ]
 [90.96 88.  ]
 [90.7  88.  ]
 [90.96 90.  ]]
```
