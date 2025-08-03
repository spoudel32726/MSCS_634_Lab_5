Purpose
The purpose of this lab was to explore and compare two clustering techniques—Agglomerative Hierarchical Clustering and DBSCAN—using the Wine dataset from sklearn. The lab emphasized:
•	Understanding how each algorithm groups data without labels.
•	Testing different parameter values to see their impact on clustering quality.
•	Evaluating clusters using metrics such as Silhouette Score, Homogeneity, and Completeness.
•	Interpreting clustering structures visually through PCA scatter plots and dendrograms.

Key Insights from Results & Visualizations
Hierarchical Clustering
•	Best Configuration: n_clusters = 3 (matches the dataset’s 3 true classes).
•	Metrics:
  o	Silhouette Score: 0.277
  o	Homogeneity: 0.790
  o	Completeness: 0.783
•	Visuals: PCA scatter plot showed three distinct, well-separated groups.
•	Interpretation: Hierarchical Clustering captured the dataset’s natural groupings effectively and was robust to small parameter changes.

DBSCAN Clustering
•	Tested Parameters: Multiple (eps, min_samples) combinations.
•	Best Tested: (eps = 2, min_samples = 3) produced 5 clusters and 64 noise points.
•	Metrics:
  o	Silhouette Score: 0.031
  o	Homogeneity: 0.442
  o	Completeness: 0.372
•	Visuals: PCA plots revealed significant noise points (gray) and smaller fragmented clusters.
•	Interpretation: DBSCAN was highly sensitive to parameter choices. It struggled with the Wine dataset’s distribution, which did not have strong density-based separation.

Comparison
•	Hierarchical Clustering outperformed DBSCAN in both metrics and interpretability.
•	DBSCAN is better suited for irregular, non-spherical clusters with varying density, but the Wine dataset’s distribution aligned more closely with the assumptions of Hierarchical Clustering.
•	Parameter sensitivity played a major role in DBSCAN results, whereas Hierarchical Clustering was more stable.

Challenges & Decisions
•	DBSCAN Parameter Tuning: Finding an eps and min_samples combination that reduced noise while capturing clusters was challenging.
•	Visualization Choices: PCA was selected to reduce dimensions for plotting, balancing interpretability with accuracy.
•	Linkage Method for HC: Ward linkage was chosen for Hierarchical Clustering due to its compatibility with Euclidean distance and better compact cluster formation.

Conclusion
•	Hierarchical Clustering is the stronger choice for the Wine dataset due to its stability, clear grouping, and high homogeneity/completeness scores.
•	DBSCAN remains a powerful algorithm for datasets with arbitrary shapes or heavy noise, but parameter sensitivity is a key challenge.


