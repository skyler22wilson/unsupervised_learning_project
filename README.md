# machine_learning_project-unsupervised-learning

## Project Goals
- The goal for this project was to garner a greater undertsanding of unsupervised learning models in both hierarchical and tradituional clustering algorithms including KMeans and Agglomerative Clustering. Additionally I wanted to utilize PCA to distill a model down into 2-3 dimensions rather than 8 while still maintining an accurate representation of the true data. 
### Project Workflow:
1. Data Cleaning:
    - There was no Null values in the data set, and upon futher examination, the values within each column made empiracle sense for what the data was trying to display
2. Exploratory Data Anlysis:
    - Created a heatmap for the correlation of each feature to identify highly correlated features, if any.
    - Iterativly produced a distribution of each feature using a histogram to understand how the data was distributed
    - Iterativly produced a box-plot for each feature to identify outliers
    - Created a pairplot of all the featrues to visually identify relationships between the features
3. Preprocessing:
    - Used a Box-Cox transformation on all of the features except Channel and Region t transform the data to be closer to a normal distribution
    - Used a Z-score to remove outliers that had a Z-score greater than 2 which suggets that they are more than 2 standard deviations from the  mean
    - Used a RobustScaler to scale the data in the dataset
4. Optimal Cluster Discovery:
    - Used an elbow diagram, Gap statistic and silouhette statistic to identify the optimal clusters for the data
5. Fit the clustering algorithms
    - Used a pairplot with the clusters as a Hue to visualize the quality of the clustering
    - Used a dendogram to identify where the hierarchical clsuteres are formed
6. used a Scree plot and percentage explained variance and cumulative explained variance to identify the optimal number of components for the PCA
7. Fit the PCA model

### Project Conclusions:
- Based on the results of the K-means and hierarchical clustering, the optimal number of clusters for the model was 2. The K value was calculated using a silohuette calculation and gap statistics. Additionally the optimal number of components that explaned over 90% of the variation in data was 3 as seen in the scree plot.
- 94.6% of the variation in the data is explained by the first 3 components, thus a model with 3 components distilled by PCA can explain nearly all of the variation of the 8 dimensional model in only 3 dimensions. While it is less accurate, just over 88% of the variation in the data can be explained with just two components which means that 88% of the data can be explained by PCA decomposed data in just gtwo dimensions rather than 8.
- The most influential features in the PCA for component 1: was Grocery, with a Loading of 0.536 and for component 2: Delicassen with a Loading of 0.623 and for component 3: Delicassen with a loading of 0.670. Interestingly the 3 most influential features were the same for components 2 and 3 which suggests that these 3 features (Delicassen, Fronzen, and Region) contribute most to the variation in those components 
- Detergents_Paper and gerocery have a strong positive correlation of 0.92 which suggests that clients of the wholesale distributor anual spending on both grocery and detergents_paper products is highly related.

### Project Challenges:
- The main challange I had with this project was correctly interpreting the values provided by the PCA. Distiling the data down into 2 or 3 features makes explaining what the effects are on the wholesale distribution complicated to explain clearly

### Future Work:
- I would like to dive into each cluster and identify and better understand how each cluster was formed and what the clustering can tell me abnout the relationships between particular products

