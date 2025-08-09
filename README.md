# MSCS_634_ProjectDeliverable_1: Customer Behavior Analysis

## Dataset Summary
This project analyzes a customer behavior dataset containing key attributes such as `Customer ID`, `Gender`, `Age`, `City`, and `Membership Type`. It also includes valuable metrics like `Total Spend`, `Items Purchased`, `Average Rating`, `Discount Applied`, `Days Since Last Purchase`, and `Satisfaction Level`. The dataset is suitable for uncovering patterns and informing business strategies related to customer engagement and loyalty.

## Major Steps Taken in Data Cleaning and Exploration

### **Data Cleaning:**
1.  **Column Renaming:** Renamed all columns to remove spaces and special characters for ease of use in Python (e.g., `Membership Type` became `Membership_Type`).
2.  **Missing Values:** Checked for missing values and imputed the missing values in `Membership_Type` using the most frequent value (mode). Rows with missing `Customer_ID`s were dropped to maintain data integrity.
3.  **Duplicates:** Identified and removed duplicate rows to ensure the dataset contains only unique records.

### **Exploratory Data Analysis (EDA):**
1.  **Feature Distribution:** Used histograms and bar plots to visualize the distribution of numerical and categorical features. This revealed that the distribution of `Total_Spend` is skewed, with a majority of customers having low spending and a few having very high spending.
2.  **Feature Relationships:** A correlation heatmap was generated to show the relationships between numerical features. This is a foundational step for identifying potential predictors for future models.
3.  **Outlier Analysis:** Box plots were used to identify outliers in columns like `Age` and `Total_Spend`, which will be handled carefully during the modeling phase.

## Key Insights and Challenges
### **Key Insights:**
* The data contains valuable information about customer spending habits and membership types, which can be used for segmentation.
* The distribution of numerical features is often skewed, suggesting that data transformation may be necessary for effective modeling.
* The relationships between features (e.g., spending and items purchased) are clear and will be critical for building predictive models.

### **Challenges Addressed:**
* **Column Names:** The original column names contained spaces, which was a significant challenge for direct indexing. This was addressed by renaming all columns at the beginning of the notebook.
* **Missing Data:** The missing values in the `Membership Type` column were a potential issue. Imputing with the mode was a sensible approach, as it preserves the overall distribution of the categorical data.
* **Data Structure:** The dataset's structure required careful inspection to ensure that the data types were correct and that the values were consistent.
