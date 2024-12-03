## Task 1

Importing pandas: Pandas is the go-to library for data manipulation in Python.
Loading the CSV file: The pd.read_csv() function reads the dataset into a DataFrame, making it easier to work with.
Inspecting the data:
.head() displays the first five rows of the dataset, helping you verify the structure and content.
.info() provides a summary of the dataset, including the number of non-null entries and data types for each column.

## Task 2

Splitting the Data:
The train_test_split() function from sklearn.model_selection is used to split the data into training and testing sets.
test_size=0.2 specifies that 20% of the data will be used for testing.
random_state=42 ensures reproducibility by fixing the random seed.

Separating Features and Target:
data.drop(columns=['Price']) removes the target column (Price) to create the feature set (X).
data['Price'] isolates the target variable, which is what we aim to predict.

Verifying the Split:
.shape on X_train, X_test, y_train, and y_test confirms that the split was done correctly.

##  Task 3a
describe() computes summary statistics like count, mean, standard deviation, min, 25th percentile, median (50%), 75th percentile, and max.
Focusing on numerical features helps quickly spot anomalies, such as unusually high maximum values or a wide range.

## Task 3b
isnull().sum() counts the number of missing entries for each column.

## Task 3c
duplicated() identifies duplicate rows in the dataset.
.sum() counts the total number of duplicates.

## Task 3d
The IQR is calculated as q3 - q1, where q1 and q3 are the 25th and 75th percentiles, respectively.
Outliers are values falling below q1 - 1.5 * IQR or above q3 + 1.5 * IQR.
Each numerical feature is checked, and the number of outliers is displayed.

## Task 4
Numerical Features:
sns.histplot() generates histograms with kernel density estimates (KDE) for smooth distributions.
The bins parameter can be set to 30 for consistent bin sizes across features.

Categorical Features:
sns.countplot() creates bar plots showing the frequency of each category.
order ensures categories are displayed in descending order of frequency for clarity.

Layout Customization:
tight_layout() optimizes the spacing between plots.
rotation=45 rotates x-axis labels for better readability in categorical plots.

## Task 5

Data Type Check:
Confirm that y_train is a continuous numerical variable (e.g., float64 or int64).

Summary Statistics:
.describe() provides insights into the central tendency, variability, and range of the target variable.

Distribution Visualization:
The histogram and KDE plot provide a visual representation of the target variable's distribution.
Look for patterns like normality or skewness in the price data.

## Task 6
Metrics Overview:
Mean Absolute Error (MAE): Measures the average absolute difference between actual and predicted values. Easy to interpret but less sensitive to outliers.
Mean Squared Error (MSE): Penalizes larger errors more than MAE, making it sensitive to outliers. Suitable when large errors are critical.
Root Mean Squared Error (RMSE): Provides a scale-consistent error metric by taking the square root of MSE.
R-squared (R²): Indicates the proportion of variance explained by the model. A value closer to 1 suggests better performance.

Baseline Predictions:
Uses the mean of the target variable (Price) as a simple baseline model for evaluation. Actual model predictions will replace this later.

## Task 7

Baseline Approach:
Predicts the mean of the target variable (Price) for all test samples. This represents the simplest possible model.

Performance Evaluation:
Compares the predictions to actual test data using metrics like MAE, MSE, RMSE, and R². These metrics set a lower benchmark that machine learning models must exceed.

Dummy Model Insight:
If a machine learning model cannot outperform this baseline, it indicates potential issues with data preprocessing, feature engineering, or model selection.

## Task 8

Feature Preprocessing:
Numerical features are standardized using StandardScaler to improve model stability.
Categorical features are one-hot encoded with OneHotEncoder to handle categorical data.

Pipeline:
Combines preprocessing steps and model training into a single pipeline for streamlined operations.

Model Training:
The LinearRegression model is fitted using the preprocessed training data.

Evaluation:
Predictions are made on the test data.
Metrics like MAE, MSE, RMSE, and R² are calculated to evaluate the model's performance.

## Task 9
Baseline Evaluation:
The baseline predictions are computed by predicting the mean of the target variable (Price) for all test samples, as shown in Task 7.

Linear Regression Model Evaluation:
The previously trained linear regression model (y_pred) is evaluated using the same metrics (MAE, MSE, RMSE, R²).

Comparison:
The performance of the baseline model is compared against the linear regression model to determine if the machine learning model outperforms the simple mean-based solution.

Visualization (Optional):
A bar plot can be created to visually compare the MAE of the baseline and linear regression model. Similar plots can be made for other metrics like MSE, RMSE, and R².
