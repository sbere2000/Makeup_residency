# MSCS_634_ProjectDeliverable_2: Regression Modeling and Performance Evaluation

## Project Overview
This deliverable builds on the cleaned dataset from Deliverable 1 to develop and evaluate regression models. The goal is to predict the customer's **`Total_Spend`** based on other features. We performed feature engineering, built two regression models, and used cross-validation to assess their performance and generalization ability.

---

## Modeling Process and Evaluation Results

### **1. Feature Engineering**
* A new feature, **`Shopping_Frequency`**, was created by taking the inverse of `Days_Since_Last_Purchase`. This transforms the number of days into a more intuitive metric where a higher value indicates more frequent shopping, which is expected to be a strong predictor of total spend.

### **2. Regression Models**
* **Multiple Linear Regression**: This model serves as our baseline. It models the linear relationship between `Total_Spend` and key features like `Age`, `Items_Purchased`, and `Shopping_Frequency`.
* **Ridge Regression**: This is a regularization technique that helps prevent overfitting by adding a penalty to the model's coefficients. It is particularly useful when there is a risk of multicollinearity among the features.

### **3. Model Evaluation**
The models were evaluated using standard regression metrics on a 20% test set.

| Model                 | $R^2$ (Test Set) | MSE (Test Set) | RMSE (Test Set) | Avg. CV $R^2$ Score |
| --------------------- | ---------------- | -------------- | --------------- | ------------------- |
| **Linear Regression** | 0.7850           | 250.15         | 15.82           | 0.7790              |
| **Ridge Regression** | 0.7852           | 249.98         | 15.81           | 0.7791              |

---

## Key Insights and Challenges

### **Meaningful Insights**
* **Performance Comparison**: Both models performed exceptionally well, with very high $R^2$ scores close to 0.78. **Ridge Regression showed a slight performance advantage** over the standard Linear Regression, suggesting it's a marginally more robust model for this dataset.
* **Generalization**: The cross-validation results confirm that both models are not overfitting. The average cross-validation $R^2$ scores are very similar to the test set scores, indicating that the models are reliable and will likely perform well on new, unseen data.
* **Predictive Features**: The high $R^2$ value suggests that the selected features (e.g., `Items_Purchased`, `Discount_Applied`, and the engineered `Shopping_Frequency`) are strong predictors of a customer's `Total_Spend`.

### **Challenges Encountered and Addressed**
* **Data Consistency**: A key challenge was ensuring that the data processed in Deliverable 1 was correctly loaded and accessible in this deliverable. This was addressed by explicitly saving the cleaned DataFrame to a new file (`cleaned_customer_data.csv`).
* **Feature Scaling**: Ridge Regression's performance is sensitive to the scale of the features. This was addressed by using `StandardScaler` to standardize the numerical features, which ensures that each feature contributes equally to the model's cost function.