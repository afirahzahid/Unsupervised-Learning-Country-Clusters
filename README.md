# HELP International: Country Clustering for Development Insights and Resources Allocation
## Project Overview
HELP International is a non-profit organization focused on providing aid to underdeveloped nations. This project aims to categorize countries based on socio-economic and health factors to identify priority areas for intervention. Using clustering techniques, I analyze patterns in the data and group countries with similar developmental attributes.

---

## Dataset
The dataset includes 167 countries and the following features:

- `child_mort`: Child mortality rate (deaths per 1,000 live births)
- `exports`: Exports as a percentage of GDP
- `health`: Health expenditures as a percentage of GDP
- `imports`: Imports as a percentage of GDP
- `income`: Average income of citizens (USD)
- `inflation`: Inflation rate (%)
- `life_expec`: Life expectancy (years)
- `total_fer`: Total fertility rate (children per woman)
- `gdpp`: GDP per capita (USD)

---

## Methods and Techniques

### 1. Exploratory Data Analysis (EDA)
- Conducted exploratory data analysis (EDA) to understand relationships and feature importance.

### 2. Data Preprocessing
- **StandardScaler**: Used to scale all numerical features for clustering algorithms.

---

## Clustering Methods

### K-Means Clustering
- **Elbow Method**: Determined the optimal number of clusters by analyzing inertia.
- **Silhouette Scores**: Evaluated cluster cohesion and separation. Best result: **5 clusters*.

### Hierarchical Clustering
- Used Ward's linkage method to construct a dendrogram.
- Agglomerative Clustering with **2 clusters** achieved the best results:

### DBSCAN
- Explored combinations of `eps` and `min_samples`
  - Best Parameters: `eps=2.5`, `min_samples=5`

### PCA + K-Means
- PCA reduced the dataset to **2 components**, retaining 90% variance.
- K-Means applied to the reduced data
  
---

## Results Summary

| Technique                | Silhouette Score | Davies-Bouldin Index |
|--------------------------|------------------|----------------------|
| K-Means                  | 0.30             | 0.867                |
| Hierarchical Clustering  | 0.315            | 1.327                |
| DBSCAN                   | 0.558            | 2.073                |
| PCA + K-Means            | 0.414            | 0.878                |


