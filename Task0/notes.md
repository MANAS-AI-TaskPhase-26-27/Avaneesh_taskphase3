# Basic Overview of Artificial Intelligence and Machine Learning

## 1. What is Artificial Intelligence?

**Artificial Intelligence (AI)** is the broad field of creating computer systems that can perform tasks that normally require human intelligence.

Examples include:

- Recognizing images
- Understanding speech
- Recommending products or videos
- Making predictions
- Answering questions
- Recognizing patterns

## 2. What is Machine Learning?

**Machine Learning (ML)** is a branch of AI in which computers learn patterns from data and use those patterns to make predictions or decisions.

Instead of programming every rule explicitly, we provide data and allow an ML algorithm to learn useful patterns.

### Example

Suppose we want to identify whether an email is spam.

The computer can be given many examples of emails that are already labelled as:

- Spam
- Not spam

The ML algorithm learns patterns from these examples and can then classify a new email.

---

# 3. Basic Machine Learning Terminology

### Features

**Features** are the input variables used by a machine learning model.

For example, when predicting house prices, features could include:

- Area
- Number of bedrooms
- Location
- Age of the house

### Label

A **label** is the known target or answer that the model is trying to predict in supervised learning.

Example:

```text
Area = 1500 sq ft
Bedrooms = 3
Location = Mumbai
Price = ₹80 lakh
```

Here:

- Features = Area, Bedrooms, Location
- Label = Price

### Example

An individual observation or row in a dataset can be called an **example**.

---

# 4. What is a Model?

A **model** is a mathematical or computational representation that learns patterns from data and uses those patterns to make predictions or decisions.

For example, a model may learn the relationship between:

- Age
- Blood pressure
- Symptoms

and the likelihood of a particular disease.

The model is trained using existing data and is then used on new data.

---

# 5. Supervised Learning

In **supervised learning**, the model learns from labelled data.

The training dataset contains both:

- Features
- Labels

## Basic Types of Supervised Learning

### 5.1 Classification

Classification predicts a **category or class**.

Examples:

- Disease / No Disease
- Spam / Not Spam
- Pass / Fail
- Benign / Malignant

### 5.2 Regression

Regression predicts a **numerical value**.

Examples:

- House price
- Temperature
- Blood pressure
- Body weight
- Hospital length of stay

### Simple Comparison

| Classification | Regression |
|---|---|
| Predicts a category | Predicts a numerical value |
| Disease / No Disease | Blood pressure |
| Spam / Not Spam | House price |
| Pass / Fail | Temperature |

---

# 6. Unsupervised Learning

In **unsupervised learning**, the data does not have predefined labels.

The algorithm attempts to identify useful patterns, groups, or relationships within the data.

## Basic Types of Unsupervised Learning

### 6.1 Clustering

**Clustering** groups similar observations together.

Example:

A dataset containing many patients may be divided into groups based on similarities in their characteristics.

Applications include:

- Customer segmentation
- Patient grouping
- Grouping similar data points

### 6.2 Association

**Association** identifies relationships or patterns between items or variables.

For example, in market basket analysis, an algorithm may identify products that are frequently purchased together.

### 6.3 Dimensionality Reduction

**Dimensionality reduction** reduces the number of features while attempting to retain important information.

For example:

```text
100 features → 10 important dimensions
```

This can help with visualization, data processing, and reducing complexity.

---

# 7. Supervised vs. Unsupervised Learning

| Feature | Supervised Learning | Unsupervised Learning |
|---|---|---|
| Labels | Available | Not available |
| Main purpose | Prediction | Pattern discovery |
| Basic types | Classification, Regression | Clustering, Association, Dimensionality Reduction |
| Example | Disease prediction | Patient grouping |

---

# 8. Training, Validation, and Test Sets

A dataset is commonly divided into three parts.

## Training Set

The **training set** is used to teach the model.

The model learns its parameters from the training examples.

## Validation Set

The **validation set** is used during model development.

It can be used to:

- Compare different models
- Tune hyperparameters
- Select an appropriate model
- Monitor generalization

## Test Set

The **test set** is used at the end to evaluate the final model using data that was not used for training.

### Important

The test set should be kept separate from model development and should not be repeatedly used to tune the model.

---

# 9. How Does Machine Learning Training Work?

At a high level, training involves the following idea:

1. The model receives training data.
2. The model makes a prediction.
3. The prediction is compared with the actual answer.
4. An error or loss is calculated.
5. The model adjusts its parameters.
6. The process is repeated.

### Simple Example

Suppose the actual house price is:

```text
₹50 lakh
```

The model predicts:

```text
₹45 lakh
```

There is an error between the predicted and actual values.

During training, the model adjusts its parameters so that its predictions can improve.

The exact training process depends on the ML algorithm being used.

---

# 10. Why Does Data Need Cleaning and Preprocessing?

Real-world data is rarely ready for direct use in a machine learning model.

Data may contain:

- Missing values
- Incorrect values
- Duplicate records
- Outliers
- Categorical variables
- Different measurement scales
- Inconsistent formats

### Data Cleaning

Data cleaning involves identifying and correcting or handling problems in the dataset.

### Data Preprocessing

Data preprocessing converts the cleaned data into a suitable form for the selected ML algorithm.

Good data preparation can improve the quality and reliability of the modelling process.

---

# 11. Handling Missing Data

Missing data occurs when information is not available.

Example:

```text
Age

21
25
NA
30
28
```

`NA` represents a missing value.

## Common Imputation Strategies

**Imputation** means replacing a missing value with an estimated or substituted value.

### Mean Imputation

A missing numerical value is replaced by the mean.

Example:

```text
20, 22, NA, 24

Mean = 22

20, 22, 22, 24
```

### Median Imputation

A missing numerical value is replaced by the median.

Median can be useful when the data contains extreme values.

### Mode Imputation

A missing categorical value is replaced by the most frequently occurring category.

Example:

```text
A, B, A, NA, A

Mode = A
```

### Other Methods

Depending on the situation, missing data may also be handled by:

- Removing observations or variables when justified
- Forward or backward filling for suitable sequential data
- Model-based imputation

The appropriate strategy depends on the amount and type of missing data and why it is missing.

---

# 12. Handling Outliers

An **outlier** is an observation that is unusually different from the other observations.

Example:

```text
20, 21, 22, 23, 24, 25, 100
```

Here, `100` may be considered an outlier.

## Common Methods for Detecting Outliers

- Box plots
- IQR method
- Z-scores
- Domain knowledge

### IQR Method

```text
IQR = Q3 − Q1

Lower limit = Q1 − 1.5 × IQR
Upper limit = Q3 + 1.5 × IQR
```

### Important

An outlier should not automatically be deleted.

It may represent:

- Data-entry error
- Measurement error
- A genuine extreme observation

The appropriate action depends on the context.

---

# 13. Categorical Encoding

Categorical variables contain categories rather than numerical measurements.

Example:

```text
Gender

Male
Female
Female
Male
```

Many machine learning algorithms require numerical input, so categorical variables may need to be converted into numerical representations.

## One-Hot Encoding

Example:

| Gender | Male | Female |
|---|---:|---:|
| Male | 1 | 0 |
| Female | 0 | 1 |
| Female | 0 | 1 |
| Male | 1 | 0 |

## Ordinal Encoding

Ordinal encoding can be used when categories have a meaningful order.

Example:

```text
Mild       → 1
Moderate   → 2
Severe     → 3
```

For categories without a natural order, such as Red, Blue, and Green, one-hot encoding is often more appropriate.

---

# 14. Feature Scaling

Features may have very different numerical ranges.

Example:

```text
Age       → 18–80
Height    → 140–200
Income    → 20,000–500,000
```

Some machine learning algorithms are affected by differences in feature scale.

## Standardization

A common method is:

```text
z = (x − mean) / standard deviation
```

## Min-Max Scaling

Values are commonly transformed to a range such as 0 to 1:

```text
x' = (x − minimum) / (maximum − minimum)
```

Feature scaling is particularly important for algorithms that depend on distances or are sensitive to the numerical scale of inputs.

Examples include:

- K-nearest neighbors
- K-means
- Support Vector Machines
- Many neural-network training setups

Tree-based models generally do not require feature scaling.

---

# 15. Overfitting vs. Underfitting

## Underfitting

Underfitting occurs when the model is too simple to capture important patterns in the data.

Typical situation:

```text
Training performance → Poor
Test performance     → Poor
```

## Overfitting

Overfitting occurs when the model learns the training data too closely, including noise or patterns that do not generalize to new data.

Typical situation:

```text
Training performance → Very good
Test performance     → Poor
```

## Good Generalization

A useful model should perform reasonably well on new, unseen data.

```text
Training performance → Good
Test performance     → Good
```

### Ways to Reduce Overfitting

- Use more representative data
- Reduce model complexity
- Regularization
- Cross-validation
- Feature selection
- Early stopping where appropriate

---

# 16. Evaluation Metrics

After training a model, we need to evaluate how well it performs.

The appropriate metric depends on the type of problem and the consequences of different errors.

## Confusion Matrix

For binary classification:

| | Predicted Positive | Predicted Negative |
|---|---:|---:|
| **Actual Positive** | TP | FN |
| **Actual Negative** | FP | TN |

Where:

- **TP** = True Positive
- **TN** = True Negative
- **FP** = False Positive
- **FN** = False Negative

## Accuracy

The proportion of all predictions that are correct.

```text
Accuracy = (TP + TN) / (TP + TN + FP + FN)
```

## Precision

Of all cases predicted as positive, how many were actually positive?

```text
Precision = TP / (TP + FP)
```

## Recall / Sensitivity

Of all actual positive cases, how many were correctly identified?

```text
Recall = TP / (TP + FN)
```

## Specificity

Of all actual negative cases, how many were correctly identified?

```text
Specificity = TN / (TN + FP)
```

## F1 Score

The harmonic mean of precision and recall.

```text
F1 = 2 × (Precision × Recall)
     / (Precision + Recall)
```

---

# 17. Regression Metrics

For regression problems, the model predicts a numerical value.

Common evaluation metrics include:

### MAE — Mean Absolute Error

Average absolute difference between actual and predicted values.

```text
MAE = Average |Actual − Predicted|
```

### MSE — Mean Squared Error

Average squared difference between actual and predicted values.

```text
MSE = Average (Actual − Predicted)²
```

### RMSE — Root Mean Squared Error

```text
RMSE = √MSE
```

### R² — Coefficient of Determination

Describes the proportion of variation in the target that is explained by the model under the specified evaluation setting.

---

# 18. Simple Example: Disease Prediction

Suppose we want to predict whether a patient has a disease.

| Age | Blood Pressure | Symptoms | Disease |
|---:|---:|---|---|
| 45 | 140 | Yes | Yes |
| 30 | 110 | No | No |
| 60 | 150 | Yes | Yes |
| 35 | 115 | No | No |

### Features

- Age
- Blood Pressure
- Symptoms

### Label

- Disease

### Basic ML Process

The data is first checked and prepared. Missing values are handled if present, categorical variables such as symptoms are encoded, and scaling is applied if required by the selected algorithm.

The dataset is then divided into training, validation, and test sets.

The model learns patterns from the training data. The validation data can be used during development, and the final model is evaluated using the test data.

For this classification problem, possible evaluation metrics include:

- Accuracy
- Precision
- Recall / Sensitivity
- Specificity
- F1 Score

---

# 19. Quick Revision Table

| Concept | Basic Meaning |
|---|---|
| AI | Broad field of creating intelligent computer systems |
| ML | Learning patterns from data |
| Feature | Input information used by a model |
| Label | Known target in supervised learning |
| Model | Learned representation used for prediction or decision-making |
| Supervised learning | Learning from labelled data |
| Classification | Predicting a category |
| Regression | Predicting a numerical value |
| Unsupervised learning | Finding patterns in unlabelled data |
| Clustering | Grouping similar observations |
| Association | Finding relationships between items or variables |
| Dimensionality reduction | Reducing the number of features |
| Training set | Used to train the model |
| Validation set | Used during model development |
| Test set | Used for final evaluation |
| Imputation | Replacing or estimating missing values |
| Outlier | Unusually different observation |
| Encoding | Converting categorical data into numerical representation |
| Feature scaling | Adjusting numerical feature scales |
| Overfitting | Good training performance but poor generalization |
| Underfitting | Model is too simple to capture important patterns |
| Accuracy | Overall proportion of correct predictions |
| Precision | Correct positives among predicted positives |
| Recall | Correct positives among actual positives |
| Specificity | Correct negatives among actual negatives |

---

# 20. Key Takeaways

1. **AI** is the broad field of creating systems capable of intelligent tasks.
2. **Machine Learning** is an approach in which computers learn patterns from data.
3. **Features** are inputs used by a model.
4. A **label** is the target value in supervised learning.
5. A **model** learns patterns from data and uses them to make predictions or decisions.
6. **Supervised learning** includes classification and regression.
7. **Unsupervised learning** includes clustering, association, and dimensionality reduction.
8. **Training data** is used to learn the model.
9. **Validation data** supports model development and tuning.
10. **Test data** is used for final evaluation on unseen data.
11. Real-world data often requires **cleaning and preprocessing**.
12. Missing values, outliers, categorical variables, and different feature scales need appropriate handling.
13. **Overfitting** occurs when a model does not generalize well to new data.
14. **Underfitting** occurs when a model is too simple to capture important patterns.
15. Evaluation metrics should be selected according to the **problem and the consequences of prediction errors**.
16. The ultimate objective is to build a model that **generalizes well to new, unseen data**.
