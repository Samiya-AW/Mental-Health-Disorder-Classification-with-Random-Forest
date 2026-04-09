# Mental-Health-Disorder-Classification-with-Random-Forest

I have implemented a complete **machine learning model to classify mental disorders** based on symptoms. The code builds a **complete ML pipeline**:

1. Data cleaning
2. Model training
3. Evaluation
4. Handling imbalance
5. Optimization
6. Interpretation

👉 End result: A **high-accuracy (~93–96%) mental disorder classification system** with improved fairness and interpretability.

---

## 1. Setup and Data Loading

* Installs and imports libraries like **pandas** and **scikit-learn**.
* Loads an Excel dataset containing symptoms and their corresponding mental disorders.
* Cleans the data by:

  * Removing missing values
  * Removing duplicate entries

---

## 2. Feature and Label Separation

* Splits the dataset into:

  * **X (features):** symptoms
  * **y (labels):** disorder type

---

## 3. Train-Test Split

* Divides data into:

  * **Training set (80%)** for learning
  * **Testing set (20%)** for evaluation
* Uses **stratified sampling** to keep class distribution balanced.

---

## 4. Initial Model Training

* Trains a **Random Forest Classifier**.
* Makes predictions on test data.
* Evaluates using:

  * **Accuracy (~91%)**
  * **Classification report** (precision, recall, F1-score per disorder)

---

## 5. Model Validation

* Uses **cross-validation (5-fold)** to check consistency.
* Gets average accuracy of about **93%**, confirming stability.

---

## 6. Confusion Matrix

* Visualizes prediction errors using a confusion matrix.
* Helps identify which disorders are misclassified.

---

## 7. Handling Class Imbalance (Key Improvement)

* Applies **SMOTE (Synthetic Minority Over-sampling Technique)**:

  * Generates synthetic samples for underrepresented disorders
  * Balances the dataset

---

## 8. Retraining with Balanced Data

* Splits the new balanced dataset again.
* Trains a new Random Forest model with:

  * `class_weight="balanced"`
* Performance improves:

  * **Test accuracy ~93%**
  * Better recall for minority classes

---

## 9. Visualization

* Plots a **heatmap confusion matrix** using matplotlib and seaborn.

---

## 10. Cross-Validation Again

* Runs cross-validation on balanced data.
* Accuracy improves further to about **95.8%**.

---

## 11. Feature Importance

* Extracts most important symptoms influencing predictions.
* Top features include:

  * Introversion
  * Increased energy
  * Negative feelings
  * Sleep issues
* Visualizes top 10 features using a bar chart.

---

## 12. Hyperparameter Tuning

* Uses **GridSearchCV** to find best model settings:

  * Tries different values for:

    * Number of trees
    * Tree depth
    * Splitting criteria
* Finds optimal parameters.
* Best cross-validation score ~**96.7%**

---

## 13. Model Explainability (SHAP)

* Uses **SHAP (SHapley Additive Explanations)**:

  * Explains how each feature affects predictions
  * Provides interpretability for the model

---
