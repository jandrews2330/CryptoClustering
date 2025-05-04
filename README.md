# CryptoClustering

This project applies **K-Means clustering** and **Principal Component Analysis (PCA)** to identify natural groupings of cryptocurrencies based on various price change percentages. Interactive plots built with `hvPlot` help visually compare clustering results from the full feature set and PCA-reduced data.

## 🧾 Data Source

- Dataset: `crypto_market_data.csv`
- Features:  
  - `price_change_percentage_24h`  
  - `price_change_percentage_7d`, `30d`, `60d`, `90d`, `200d`, `1y`, etc.
- Index: `coin_id` (unique cryptocurrency name)

---

## ⚙️ Technologies Used

- Python  
- pandas, scikit-learn (KMeans, PCA, StandardScaler)  
- hvPlot for interactive visualizations  
- Jupyter Notebook  

---

## 📈 Clustering Process

### 🔹 Step 1: Normalize the Data

Used `StandardScaler` to scale features for fair clustering.

---

### 🔹 Step 2: Elbow Method (Original Scaled Data)

- Ran K-Means with `k` from 1 to 11
- Plotted **Elbow Curve**
- **Optimal `k` = 4** based on inflection point

---

### 🔹 Step 3: Cluster Cryptocurrencies (Original Data)

- Fit KMeans with `k=4` on scaled data
- Predicted clusters
- Visualized clusters using:
  - `x = price_change_percentage_24h`  
  - `y = price_change_percentage_7d`

---

### 🔹 Step 4: Apply PCA
Reduced dimensions to 3 components

Explained variance:

PC1: 37.2%

PC2: 34.7%

PC3: 17.6%

**Total Explained Variance**: **89.5%**

---

### 🔹 Step 5: Elbow Method (PCA Data)
Ran K-Means on PC1, PC2, PC3

**Optimal k still = 4**

Slightly different inertia values but same cluster count

---

### 🔹 Step 6: Cluster Using PCA Data
Fit KMeans with k=4 on PCA output

Visualized clusters using:
  - `x = PC1`
  - `y = PC2`

## 📊 Visualizations
### 🔸 Elbow Curve Comparison
Side-by-side elbow curves:

Original data

PCA-reduced data

### 🔸 Cluster Comparison
Scatter plots comparing:

Clusters using all features

Clusters using PCA-reduced data

---

## Acknowledgments: 
**Prepared using provided dataset and Jupyter notebook, consulted prior class examples and Xpert Learning Assistant.**