# Credit-Card-Customer-Segmentation-for-Marketing-Strategy-Development
This project aims to develop a customer segmentation model for a credit card company using the usage behavior of 9,000 active cardholders over six months. The goal is to use the segmentation to inform targeted marketing strategies and help the company understand customer groups to tailor marketing efforts effectively.

---

### 1. Data Exploration and Initial Insights

- Data Loading:
  - Imported credit card data from a CSV file into a DataFrame using pandas.
- Initial Data Display:
  - Printed the first few rows of the DataFrame for a preview.
- Missing Values Check:
  - Analyzed the DataFrame for missing values using .isnull().sum().
  - Displayed the count of missing values for each column.

<img src="https://github.com/user-attachments/assets/a8676adb-12b8-4bd5-807b-df58cb88ff4a" width="200">

- Median Calculation:
  - Computed the median for MINIMUM_PAYMENTS.
  - Computed the median for CREDIT_LIMIT.
- Handling Missing Values:
  - Filled missing values in MINIMUM_PAYMENTS with its median.
  - Filled missing values in CREDIT_LIMIT with its median.
- Final Missing Values Check:
  - Re-checked for missing values post imputation and displayed results.

<img src="https://github.com/user-attachments/assets/2dda0a02-14db-427a-ba7e-24d3f69799e1" width="200">

- Data Display:
  - Displayed the entire DataFrame or its head for visual inspection.

---

### 2. Standardization and Clustering Analysis

- Standardization:
  - Standardized the numeric columns using StandardScaler.
- Elbow Method for Clustering:
  - Calculated inertia values for KMeans clustering with cluster numbers ranging from 1 to 10.
  - Plotted elbow curve to determine the optimal number of clusters.
  - **Identified optimal point to be 4 clusters**

![image](https://github.com/user-attachments/assets/106bfc25-10d3-4b4c-b996-ba73d5e0b8a8)

- KMeans Clustering:
  - Performed KMeans clustering with 4 clusters on standardized data.
  - Adjusted cluster labels to start from 1.
- Cluster Information Creation:
  - Created a new DataFrame (creditcard_cluster) containing customer IDs and their cluster labels.
- Data Display:
  - Printed the first few rows of the creditcard_cluster DataFrame for verification.

![image](https://github.com/user-attachments/assets/a6510770-3236-4a9f-8913-7ea0232db41a)
