## Task 1
Importing pandas: Pandas is the go-to library for data manipulation in Python.
Loading the CSV file: The pd.read_csv() function reads the dataset into a DataFrame, making it easier to work with.
Inspecting the data:
Loading the dataset: The dataset is loaded using pd.read_csv(), which reads the CSV file and converts it into a pandas DataFrame.
Displaying the first few rows: data.head() helps to preview the first five rows of the dataset to understand its structure.
General information: data.info() provides information about the dataset, such as the number of rows, columns, and data types.



## Task 2
Feature and Target Split: X contains the features (all columns except Fraud), and y contains the target variable (Fraud).

train_test_split: The train_test_split function is used to randomly split the data into training and testing sets. The test_size=0.2 argument specifies that 20% of the data will be used for testing, and 80% will be used for training. The random_state=42 ensures that the split is reproducible, and stratify=y ensures that the class distribution (fraud vs. non-fraud) is maintained in both the train and test sets.

Shape Check: The shape method is used to verify the size of the training and testing sets to ensure the split was successful.

## Task 3a

Identify missing values in the training set.
Handle missing values in the categorical features by replacing them with the most frequent value (mode).
Handle missing values in the numerical features by replacing them with the mean value.

## Task 3b

Identify outliers in the numerical features using the Interquartile Range (IQR) method.
Clip values that fall outside of the acceptable range (below the lower bound or above the upper bound) to the nearest acceptable value.

## Task 3c
Check the class distribution of the target variable (Fraud).
Apply undersampling to balance the class distribution.

## Task 4
Visualizing Continuous Features:
For each continuous feature (e.g., Transaction_Amount, Transaction_Time, Card_Balance), a histogram is plotted with a Kernel Density Estimate (KDE) to show the distribution of the feature values. This helps identify patterns like skewness or multi-modal distributions.

Visualizing Categorical Features:
For each categorical feature (e.g., Transaction_Type, Transaction_Method), a count plot is created to show the distribution of the categories in the feature. This helps identify any class imbalances or unusual distributions in categorical data.

Skewness Analysis:
The skewness of each continuous feature is computed using scipy.stats.skew(). If the skewness is greater than 1 or less than -1, it indicates that the feature is highly skewed, and a transformation might be necessary (e.g., log transformation or square root transformation) to normalize the distribution.

## Task 5:
Steps to Complete the Task:
Accuracy: This is the most commonly used metric but might not be the best in the case of imbalanced datasets.
Precision: Precision helps us understand the percentage of predicted fraudulent transactions that are actually fraudulent.
Recall: Recall is important for fraud detection because it measures how many of the actual fraud cases we can identify.
F1-Score: The harmonic mean of precision and recall. It balances the two and is often used when precision and recall are both important.
ROC AUC: Measures the model’s ability to distinguish between classes. It’s a good metric for imbalanced datasets and gives insight into the model’s performance at various thresholds.

## Task 6
Baseline Model:
The baseline model simply predicts 0 (non-fraudulent) for every transaction in the test set. This is the simplest possible model and serves as a reference point to evaluate the performance of more sophisticated models.

Evaluation of Baseline:
The same classification metrics (accuracy, precision, recall, F1-score, and ROC AUC) are calculated for the baseline model. This allows us to assess its performance.

## Task 7
Feature Transformation:
Categorical features (Transaction_Type, Transaction_Method) are encoded using OneHotEncoder to create binary columns for each category.
Continuous features (all columns except categorical ones) are normalized using StandardScaler to ensure they have a mean of 0 and a standard deviation of 1.

Pipeline:
A Pipeline is used to apply the transformations and then fit the logistic regression model sequentially. This allows for a streamlined process where the same transformations are applied consistently during training and testing.

Train-Test Split:
The dataset is split into training and testing sets (80% training, 20% testing). The model is trained on the training set and evaluated on the testing set.

Model Training and Prediction:
The logistic regression model is trained using the pipeline (pipeline.fit()) and used to predict the target variable for the test data.

Model Evaluation:
The model’s performance is evaluated using several classification metrics such as accuracy, precision, recall, F1-score, and ROC AUC. These metrics help assess the model’s effectiveness, especially in an imbalanced dataset like fraud detection.

## Task 8:
Logistic Regression Model Evaluation:
The code evaluates the logistic regression model using the same classification metrics (accuracy, precision, recall, F1-score, and ROC AUC) as in Task 6 and Task 7. These metrics provide insights into how well the logistic regression model performs on the test data.

Comparison with Baseline:
The code compares the performance of the logistic regression model with the baseline no-ML solution. The baseline, which predicts 0 for all cases (non-fraudulent transactions), serves as a simple reference point.

Interpretation of Results:
After printing the evaluation metrics for both the logistic regression model and the baseline, the code provides a brief interpretation. This helps students understand how the metrics reflect the performance of both models and why machine learning can be valuable, especially in fraud detection tasks where the classes are imbalanced.
