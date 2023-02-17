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
In order to find out which rows are having missing values and whether to keep them for analysis or remove them, we divide the data into two subsets: one for data points that are above some threshold for missing values, and a second subset for points below that threshold.

### Selection and Re-encoding of Features:

## Feature Transformation steps:

### Applying feature scaling:

### Performing Dimensionality Reduction:

### Interpreting Principle Components:

## Clustering applied on the general demographic data and the company customer data:

## Results:


