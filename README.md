# Customer Segmentation Study — Unsupervised Learning & Clustering

## 📌 Project Overview
This project focuses on segmenting retail customers using unsupervised machine learning techniques. The UCI Online Retail dataset is used to analyze customer purchasing behaviour and identify meaningful customer groups using RFM analysis and K-Means clustering.

## 🎯 Objectives
- Analyze customer purchasing behaviour.
- Calculate Recency, Frequency, and Monetary (RFM) features.
- Apply feature scaling before clustering.
- Determine a suitable number of clusters using the Elbow Method and Silhouette Score.
- Apply K-Means clustering to identify customer segments.
- Visualize customer groups using Principal Component Analysis (PCA).
- Develop customer personas and suggest suitable marketing strategies.

## 📊 Dataset
**Dataset Name:** UCI Online Retail Dataset

**Source:** [UCI Machine Learning Repository — Online Retail](https://archive.ics.uci.edu/dataset/352/online+retail)

The dataset contains retail transaction records, including invoice numbers, product details, quantities, invoice dates, prices, and customer IDs.

## 🛠️ Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab / Jupyter Notebook

## 🔍 Project Workflow

### 1. Data Cleaning
- Remove records with missing Customer IDs or invoice dates.
- Exclude cancelled invoices.
- Remove transactions with non-positive quantities or prices.
- Calculate total transaction amount.

### 2. RFM Feature Extraction
- **Recency:** Number of days since the customer's last purchase.
- **Frequency:** Number of distinct invoices placed by the customer.
- **Monetary:** Total amount spent by the customer.

### 3. Feature Scaling
Apply a logarithmic transformation to reduce skewness and use `StandardScaler` to standardize the RFM features before distance-based clustering.

### 4. Optimal Cluster Selection
- **Elbow Method:** Examine changes in within-cluster inertia.
- **Silhouette Score:** Evaluate how well-separated the clusters are.

Both methods are considered when choosing a suitable cluster count.

### 5. K-Means Clustering
Apply the K-Means algorithm to group customers according to their RFM behaviour.

### 6. Visualization
Use PCA to project the scaled RFM features into two dimensions. RFM distribution plots are also used to compare the clusters.

### 7. Customer Persona Analysis
Interpret each cluster using its customer count, average Recency, Frequency, and Monetary values. Use these profiles to develop meaningful customer personas.

## 📈 Expected Insights
- Identify recently active customers.
- Discover frequent purchasers.
- Recognize high-spending customers.
- Identify potentially inactive customers.
- Support customer retention and targeted marketing strategies.

Actual segments and findings are determined by running the notebook and reviewing its results.

## ✅ Actual Clustering Results

The analysis selected **2 clusters** based on the highest Silhouette Score among the tested values.

- **Best Silhouette Score:** 0.4329
- **Cluster 0:** 2,671 customers (61.57%); average Recency: 134.14 days, Frequency: 1.67 invoices, Monetary: 497.74.
- **Cluster 1:** 1,667 customers (38.43%); average Recency: 25.88 days, Frequency: 8.44 invoices, Monetary: 4,548.26.

Cluster 0 represents customers with lower purchase frequency and spending, while Cluster 1 represents more recently active, frequent, and higher-spending customers. These are preliminary interpretations based on average RFM values.

## 📁 Project Deliverables
- `Customer_Segmentation.ipynb` — complete analysis and clustering pipeline.
- `customer_rfm_clusters.csv` — customer-level RFM values and cluster assignments.
- `cluster_profile_summary.csv` — aggregate statistics for each cluster.
- `customer_persona_summary.csv` — cluster profiles and draft persona labels.

## 🧮 Mathematical Justification
K-Means minimizes the within-cluster sum of squared distances:

**J = Σᵢ Σₓ∈Cᵢ ||x − μᵢ||²**

Here, `Cᵢ` represents a cluster and `μᵢ` represents its centroid.

Feature scaling is necessary because Euclidean distance is sensitive to differences in feature scales. The Elbow Method helps assess diminishing improvements in inertia as the number of clusters increases, while the Silhouette Score evaluates cluster separation and cohesion.

## ⚠️ Limitations
- RFM features do not capture demographics, customer satisfaction, or all aspects of purchasing behaviour.
- K-Means is sensitive to outliers, feature scaling, initialization, and cluster count.
- The Elbow Method can be subjective, and the highest Silhouette Score may not always produce the most actionable business segments.
- PCA reduces dimensions for visualization and may hide some separation present in the original feature space.
- Customer behaviour may change over time.
- The dataset represents one retailer and may not generalize to all businesses.

## ▶️ How to Run
1. Open `Customer_Segmentation.ipynb` in Google Colab or Jupyter Notebook.
2. Run the notebook cells in order.
3. Allow the dataset to load and the analysis to complete.
4. Review the Elbow and Silhouette plots.
5. Inspect the cluster profiles and customer personas.
6. Download the generated CSV files.

## 🏁 Conclusion
This project demonstrates how RFM analysis and K-Means clustering can be combined to understand retail customer behaviour. The resulting customer segments can help businesses develop targeted marketing, retention, and loyalty strategies.

**Note:** Final cluster counts, scores, and persona descriptions should be reported only after running the notebook and validating the actual results.
