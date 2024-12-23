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

--- 

### 3. Conducting Principal Component Analysis (PCA)
- PCA Initialization:
  - Initialized PCA with 10 components.
- PCA Transformation:
  - Performed PCA on the standardized numeric columns, resulting in a PCA component matrix.
- PCA DataFrame Creation:
  - Created a DataFrame (pca_df) to hold PCA components and included CUST_ID and Cluster from the original dataset.
- Initial PCA Results Display:
  - Printed the first few rows of the PCA DataFrame for verification.
- PCA Loadings Retrieval:
  - Extracted loadings for the first four principal components and organized them in a DataFrame for clarity.
- Display PCA Loadings:
  - Displayed the loadings to show feature contributions to each principal component.
- Specific PCA Loadings for PC1:
  - Retrieved and displayed loadings specifically for the first principal component (PC1).
- Combined PCA Loadings for PC1 and PC2:
  - Retrieved loadings for both the first (PC1) and second (PC2) principal components and combined them in a DataFrame.
- Final Display of Combined Loadings:
  - Printed the combined loadings for PC1 and PC2 to evaluate feature contributions.

![3](https://github.com/user-attachments/assets/acc37e44-f60b-4c19-a16e-4d4b6ec7e27d)

--- 

### 4. Clustering and Principal Component Analysis (PCA) Visualization
- Visualization of Cluster Means:
  - Plotted bar charts displaying the mean values of each feature grouped by clusters.
  - Specifically highlighted the mean of PC1 across clusters in a separate bar chart.
- Feature Means Across Clusters Visualization:
  - For each selected numeric feature, created individual bar charts showing the mean values per cluster.

![a](https://github.com/user-attachments/assets/c8dc8494-eee4-4cea-8790-7b4b4a8c74ec)
![aa](https://github.com/user-attachments/assets/31491276-c8f1-4f73-98c0-65dd4f335366)
![aaa](https://github.com/user-attachments/assets/7145a1e9-2cf7-483c-b2c9-7283ebb02c4b)
![aaaa](https://github.com/user-attachments/assets/31a8e58c-ab22-457e-934e-e3eb03dfb3ba)

- PCA1 Mean Visualization:
  - Reiterated the visualization of the mean of PC1 by cluster to emphasize differences in PCA components across the clusters.

![b](https://github.com/user-attachments/assets/d90a6e90-3fbb-4f3f-9e54-3cfc961d101e)

---

### 5. Summary of Analysis Steps and Results

- Feature Mean Analysis:
  - Printed mean values for each feature grouped by cluster, providing insight into the average metrics within each clustered group.
  - Printed mean values for the first principal component (PC1) by cluster to highlight differences in PCA representation among clusters.

![d](https://github.com/user-attachments/assets/c5465c37-9810-428b-874c-7f2ac758d1ad)
![dd](https://github.com/user-attachments/assets/3043558d-a094-4082-ab3f-505ecbcd10ac)
![ddd](https://github.com/user-attachments/assets/2a230af8-068d-454d-a64c-9f4cf90e88da)


- Visualization:
  - Created scatter plots for PCA1 versus PCA2, color-coded by cluster, and included descriptive labels for each cluster to facilitate interpretation of the clustered data patterns.

![c](https://github.com/user-attachments/assets/160fcbc4-cde4-461a-a0b8-c88e7759242b)


- Data Export:
  - Prepared to save the updated dataset, including cluster assignments, for future analysis or reporting.
    > CC_with_Clusters.csv 

---

### 6. Interpretation of Clusters, Insights, and Marketing Strategy Development 

 - ​Cluster 1: Low Balance & Inactive Users
   - BALANCE: -0.6999 (very low balance)
   - BALANCE_FREQUENCY: -1.9718 (rarely or never use credit)
   - PURCHASES: -0.3062 (low purchasing activity)
   - CASH_ADVANCE: -0.3243 (minimal cash advances)
   - PURCHASES_FREQUENCY: -0.4271 (low frequency of purchases)
   - CREDIT_LIMIT: -0.2338 (low credit limit)
   - MINIMUM_PAYMENTS: -0.2884 (low minimum payments)
   - PRC_FULL_PAYMENT: 0.3410 (moderate full payment percentage)
   - Cluster 1 represents users who have low credit card usage and balances. Their minimal credit usage, alongside moderate full payment percentage, indicates they may be cautious users who are not heavily reliant on credit cards, possibly using them for occasional purchases while paying off their balances with some consistency.

   - Marketing Strategy/Strategic Actions:
     - Incentives: Introduce cashback offers, low-interest rates, or zero-interest periods.
     - Engagement: Send personalized campaigns and reminders for unused credit.
     - Education: Provide financial resources on credit card benefits.
     - Credit Growth: Offer credit limit increases for responsible usage.
​
- Cluster 2: Moderate Credit Users with Balanced Financial Activity
  - BALANCE: -0.1491 (moderate balance.
  - BALANCE_FREQUENCY: 0.4109 (moderate balance usage)
  - PURCHASES: 0.5512 (moderate purchasing activity)
  - CASH_ADVANCE: -0.3550 (low cash advance usage)
  - PURCHASES_FREQUENCY: 1.0906 (moderate frequency of purchases)
  - CREDIT_LIMIT: 0.1717 (moderate credit limit)
  - MINIMUM_PAYMENTS: -0.0285 (almost no minimum payments, indicating good payment habits)
  - PRC_FULL_PAYMENT: 0.4425 (moderate full payment percentage)
  - Cluster 2 consists of users with moderate credit usage, showing responsible financial behavior. Their moderate PRC_FULL_PAYMENT and low minimum payments indicate they are proactive in paying off their balances. This group represents a well-managed consumer base, likely to benefit from targeted offers for higher credit limits or loyalty programs.

  - Marketing Strategy/Strategic Actions:
    - Retention: Implement loyalty programs with tailored rewards.
    - Promotions: Offer exclusive discounts and seasonal deals.
    - Upselling: Introduce premium card options with additional benefits.
    - Credit Adjustment: Reward consistent usage with credit limit increases.
    - Tools: Promote financial planning and budgeting tools.
​
- Cluster 3: Minimal Credit Usage with Low Cash Advances
  - BALANCE: -0.0355 (low balance)
  - BALANCE_FREQUENCY: 0.3746 (moderate balance usage)
  - PURCHASES: -0.3374 (low purchasing activity)
  - CASH_ADVANCE: -0.0934 (minimal cash advances)
  - PURCHASES_FREQUENCY: -0.7054 (low frequency of purchases)
  - CREDIT_LIMIT: -0.3526 (low credit limit)
  - MINIMUM_PAYMENTS: -0.0174 (very low minimum payments)
  - PRC_FULL_PAYMENT: -0.4467 (low full payment percentage)
  - Cluster 3 represents users with minimal credit card usage but a slightly higher level of engagement than Cluster 1. While their purchasing frequency and credit usage are still low, the group occasionally takes cash advances and carries balances. The low PRC_FULL_PAYMENT suggests these users may prefer to carry some debt over time rather than paying off balances entirely.

  - Marketing Strategy/Strategic Actions:
    - Reactivation: Run campaigns with sign-up bonuses and low-barrier challenges.
    - Feedback: Use surveys to understand inactivity reasons.
    - Incentives: Waive fees to reduce usage barriers.
    - Education: Highlight credit card advantages like credit score building.
​
- Cluster 4: High-Value & Premium Users
  - BALANCE: -0.0355 (low balance)
  - BALANCE_FREQUENCY: 0.3746 (moderate balance usage)
  - PURCHASES: -0.3374 (low purchasing activity)
  - CASH_ADVANCE: -0.0934 (minimal cash advances)
  - PURCHASES_FREQUENCY: -0.7054 (low frequency of purchases)
  - CREDIT_LIMIT: -0.3526 (low credit limit)
  - MINIMUM_PAYMENTS: -0.0174 (very low minimum payments)
  - PRC_FULL_PAYMENT: -0.4467 (low full payment percentage)
  - Cluster 4 represents high-value users with large credit limits and significant engagement. While their purchase activity is low, the group heavily relies on cash advances, suggesting they use credit for larger, emergency transactions or short-term liquidity needs. Their low PRC_FULL_PAYMENT indicates they may carry higher balances over time, potentially offering opportunities for premium services or lending products.

  - Marketing Strategy/Strategic Actions:
    - Premium Rewards: Offer VIP benefits such as lounge access and luxury experiences.
    - Personalized Services: Provide financial advisory and spending optimization tools.
    - Flexibility: Enable customized installment plans and longer grace periods.
    - Exclusive Access: Early access to new products and tailored high-value offers.
    - Milestones: Create reward levels for continued engagement and spending milestones.
