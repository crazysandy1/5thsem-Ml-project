# 5thsem-Ml-project
Hybrid Weighted Adaptive K-means for Customer Segmentation
# Hybrid Weighted Adaptive K-means for Customer Segmentation

## Project Idea
This project demonstrates a customer segmentation analysis using a novel **Hybrid Weighted Adaptive K-means** algorithm. The primary goal is to segment mall customers based on their age, annual income, and spending score to identify distinct customer groups, which can then inform targeted marketing strategies. The custom K-means implementation aims to provide more robust and meaningful clusters compared to standard K-means by incorporating domain-specific weighting and adaptive centroid merging.

## Code Uniqueness & Methodology

### 1. Weighted Distance Metric
Unlike traditional K-means which uses Euclidean distance, this implementation introduces a `weighted_distance` function. This allows assigning different importance (weights) to features during cluster assignment. In this notebook, `Annual Income (k$)` and `Spending Score (1-100)` are given higher weights (0.3 and 0.5 respectively) compared to `Age` (0.2), reflecting their potentially higher significance in defining customer segments for marketing.

### 2. Adaptive Centroid Merging
The `hybrid_kmeans` algorithm includes a `merge_centroids` function. This function dynamically merges centroids that are too close to each other based on a calculated threshold (`alpha * np.mean(dists)`). This adaptive merging step helps prevent over-segmentation and leads to a more optimal and interpretable number of clusters, even when initialized with a higher `K_init`.

### 3. Custom Segmentation Logic
Beyond just clustering, the notebook includes a `label_segment` function that assigns human-readable labels (e.g., "Premium Customers", "Potential Upsell Customers") to each cluster based on their average income and spending score. This translates raw cluster data into actionable business insights.

### 4. Comprehensive Analysis
The notebook performs a comprehensive analysis including:
- Data loading and preprocessing (standardization).
- Implementation of the custom `hybrid_kmeans` algorithm.
- Comparison with standard `KMeans` from `sklearn` using SSE (Sum of Squared Errors).
- Detailed summary of each identified customer segment (average age, income, spending, and assigned segment label).
- Visualization of cluster distribution and characteristics.

## How to Use

1.  **Dependencies**: Ensure you have the following libraries installed:
    -   `pandas`
    -   `numpy`
    -   `matplotlib`
    -   `sklearn`

2.  **Data**: The notebook expects a CSV file named `Mall_Customers.csv` in the same directory, containing customer data with 'Age', 'Annual Income (k$)', and 'Spending Score (1-100)' columns.

3.  **Run the Notebook**: Execute all cells in sequential order. The output will include:
    -   Customer segment insights with descriptive labels.
    -   A comparison of SSE between Hybrid K-means and Standard K-means.
    -   Visualizations of the clusters.

## Results and Insights
The notebook identifies distinct customer segments such as "Premium Customers", "Potential Upsell Customers", "Young Impulsive Shoppers", and "Budget Customers". The custom hybrid algorithm provides an alternative approach to segmentation that incorporates domain knowledge through feature weighting and refines the number of clusters through adaptive merging, which can lead to more business-relevant groupings.

## Visualizations
Included are plots to visualize the clusters based on Annual Income vs. Spending Score, customer distribution across clusters, and percentage distribution of customers by cluster.
