# Customer-Segmentation-using-Clustering-and-PCA-techniques

## Project Objective
In this project, the general population is segmented into groups with similar demographic properties through K-means clustering. Then, I have examined how the people in the company's customers dataset fit into those created clusters. As a result we can figure out which clusters of the general population are potential customers of the company and which sections of the population is less likely to be a customer. 

## Data Understanding 
There are four files associated with this project: 
- Udacity_AZDIAS_Subset.csv: Demographics data for the general population of Germany; 891211 persons (rows) x 85 features (columns).
- Udacity_CUSTOMERS_Subset.csv: Demographics data for customers of a mail-order company; 191652 persons (rows) x 85 features (columns).
- Data_Dictionary.md: Detailed information file about the features in the provided datasets.
- AZDIAS_Feature_Summary.csv: Summary of feature attributes for demographics data; 85 features (rows) x 4 columns

## Data Preprocessing

### Assesing Missing Data:  

#### Step 1: Convert Missing Value Codes to NaNs
The fourth column of the feature attributes summary (loaded in above as feat_info) documents the codes from the data dictionary that indicate missing or unknown data. While the file encodes this as a list (e.g. [-1,0]), this will get read in as a string object. Hence, the data has been converted so that it matches a 'missing' or 'unknown' value code into a numpy NaN value. Then, I observed how much data takes on a 'missing' or 'unknown' code, and how much data is naturally missing, as a point of interest.

#### Step 2: Assessing missing data in each column 
In order to inspect how much missing data is present in each column, as there are a few columns that are outliers in terms of the proportion of values that are missing, we try to find, identify and document these columns. While some of these columns might have justifications for keeping or re-encoding the data, for this project we decide to remove them from the dataframe for simplicity of analysis. 

#### Step 3: Assesing missing data in each row
In order to find out which rows are having missing values and whether to keep them for analysis or remove them, we divide the data into two subsets: one for data points that are above some threshold for missing values, and a second subset for points below that threshold. Afterwards, we continue the analysis with the part of the dataset having few or no missing values.

### Selection and Re-encoding of Features:
Since the unsupervised learning techniques to be used will only work on data that is encoded numerically, we need to make a few encoding changes or additional assumptions to be able to make progress. For the dataset under consideration, special handling is necessary for particularly two variable types: categorical, and 'mixed'.

## Feature Transformation steps:

### Applying feature scaling:
Before we apply dimensionality reduction techniques to the data, we need to perform feature scaling so that the principal component vectors are not influenced by the natural differences in scale for features. sklearn requires that data not have missing values in order for its estimators to work properly. So, before applying the scaler to your data, make sure that you've cleaned the DataFrame of the remaining missing values.

### Performing Dimensionality Reduction:
On the scaled data, using sklearn's PCA class we apply principal component analysis (PCA) on the data, thus finding the vectors of maximal variance in the data. Then we inspect the ratio of variance explained by each principal component as well as the cumulative variance explained. The cumulative or sequential values were also plotted using matplotlib's plot() function. Based on what is ound, a value is selected for the number of transformed features to retain for the clustering part of the project.

### Interpreting Principle Components:
After getting the transformed principle components, we see the weight of each variable on the first few components to see if they can be interpreted in some fashion.

## Clustering applied on the general demographic data and the company customer data:
To see how the data clusters in the principal components space, k-means clustering is applied to the dataset and we use the average within-cluster distances from each point to their assigned cluster's centroid to decide on a number of clusters to keep.

Now 

## Results:


