# Busienss Travel Segmentation - K Means , Agglomerative, and PCA

A focused clustering analysis in Python to segment business travelers based on yearly travel frequency and annual travel budget.
The workflow included KMeans and Agglomerative Clustering, followed by PCA-based dimensionality reduction to assess stability and variance retention.
The findings revealed three clear traveler profiles with distinct spending and travel patterns, providing actionable insights for targeted marketing and personalized service strategies.

## Objectives
- Segment travelers into distinct groups based on yearly trip frequency and travel budget.

- Compare KMeans and Agglomerative Clustering outcomes for consistency.

- Use PCA to assess the stability of clustering structure and variance preservation.

- Identify behavioral profiles to inform marketing and loyalty strategies.

## Data 
**Datasets:**
- Rows: 1,000
- Columns: 5
- Clustering Variables:
  - `yearly_trips` - Number of trips taken per year.
  -  `budget` - Annual travel budget
- Other available features: `loyalty_score` , `airline_choice_index` , `hotel_preference_score`

## Data Preparation
- Imported CSV data into pandas DataFrame
- Verified dataset had no missing values.
- selected `yearly_trips` and `budget` for clustering to focus on core travel behavior metrics. 


**Source** 
Raw Data  [Excel_Datafile](https://github.com/shriya2911/Customer-Segmentation/commit/d99b192876cde7f8b27dfef81626b920ba7bcb7f)

## Choosing the Number of Clusters- Elbow Method 
- The Elbow Method was applied to determine the optimal number of clusters. The plot of within-cluster sum of squares (intertia) versus k, shows a sharp decline from k=1 to k=3, after which the curve flattens significantly. This “elbow” at k = 3 indicates that adding more clusters yields diminishing returns in explaining data variance.

- Selecting 3 clusters achieves a strong balance between model simplicity and segment distinctiveness, ensuring that the clustering remains interpretable while capturing meaningful traveler behaviors.
  
- The elbow at k=3 indicates that adding more cluster yields diminishing returns in explaoning data variance.

## Clustering — KMeans (Before PCA)
The initial KMeans clustering on yearly_trips and budget produced three well-separated clusters.
The plot below demonstrates clear group boundaries, validating the choice of input variables and confirming that business travelers fall into distinct behavioral segments.


**Cluster Profiles:** 

- High-Spend, Infrequent Travelers

  - Highest average budgets, low trip frequency.

  - Likely executive or premium clients; value luxury over volume.

- Low-Spend, Infrequent Travelers

  - Lowest budgets and trip counts.

  - Price-sensitive, occasional travelers.

- High-Frequency, Moderate-Spend Travelers

  - Travel most often, with mid-range budgets.

  - Possibly sales, consulting, or regional operations professionals.

## PCA Analysis & Post-PCA Clustering

- To test the stability of the clustering structure, Principal Component Analysis (PCA) was applied.
- The transformation retained ~100% of the total variance, indicating no information loss.
When KMeans clustering was performed on the PCA-transformed data, the results perfectly matched the original clusters, as confirmed by a one-to-one mapping in the confusion matrix.
- This validates that the clusters are robust and independent of coordinate orientation.

## Key Insights
- **Clear Segmentation:** Distinct separation in both budget and trip frequency across clusters.
- **Stable Groupings:** Low intra-cluster spread and high inter-cluster distance confirm stability.
- **PCA Validation:** Identical cluster assignments before and after PCA confirm robustness.

## Recommendations
- Targeted Marketing Campaigns:
  - Premium offers for high-spend travelers (business-class upgrades, luxury hotel packages).
  - Loyalty discounts for high-frequency travelers.
  - Budget-friendly bundles for low-spend travelers.
- Service Personalization:
  - Tailor airline and hotel partnerships to match each cluster's preferences.
  - Implement tiered loyalty programs to incentivize upgrades.
- Future Data Enrichment:
  - Incorporate loyalty scores, airline/hotel preference metrics.
  - Explore seasonal patterns in travel frequency for more nuanced segmentation.

  

