# README WILL BE COMPLETED ASAP

# Product Review Sentiment Analysis

> Authors: Aaron Lin, Banff Jiang, Cathy Wu, Darren Banh

## Project Description
A transparent process of building a model that can identify and categorize sentiments of products in the Cell Phones & Accessories subcategory of Amazon reviews.

> Note: Size of the original dataset was reduced in order for it to be run it locally

## Installation/Usage
#### Installation:
   1. Visit the github repository at: [Product Review Sentiment Analysis](https://github.com/aaronlin79/Product-Review-Sentiment-Analysis)
   2. Click the green <> Code button in the upper right part of the screen
   3. It will reveal a drop-down menu, and make sure it is on the HTTPS tab. Copy the listed URL.
   4. Open up VSCode (make sure you are in your home directory) and run the command (replacing \<clone-url> with the copied URL):
      ```
      git clone --recursive <clone-url>
      ```
   5. If you see the files and folders load in, then you are good to go!

#### Usage:
   1. Run all cells in *CS105 Final Project.ipynb* (for simplicity, the code has been compiled into a single cell)
   2. Parts of the model that can be modified:
         - Dataset sample size (max_reviews is currently set to 1,000, but be cautious about enlarging it too far, as the K-Nearest Neighbors model may be affected)
         - Word dictionaries for positive/negative sentiments
         - k value for K-Means Clustering

## Data Cleaning
   1. Removed sections
         - Only kept relevant sections: "product/title", "review/text", "review/score"
   2. Removed section titles
         - Only kept contents of the file: product name, review, review score (out of 5)
   3. Removed stopwords
         - Utilized NTLK library as reference to remove stopwords
   4. Removed punctuation
         - Only kept periods to distinguish between sentences
   5. Converted to lowercase
         - For the sake of word dictionaries, we converted all letters to lowercase
   6. Wrote all changes to *cleaned_reviews.txt*
         - Wrote to new files with each step, but final file that we input to the model is *cleaned_reviews.txt*

## Data Preprocessing
We limited the size of the dataset (originally 10,000,000+ observations) to 1,000 observations in order to run the models locally

## Data Processing
#### Text Representation:
<ins>Bag-of-Words (BoW):</ins><br>
We opted for this method due to its straightforward implementation and its compatibility with our word dictionaries. Since we have removed stopwords and are prioritizing the presence of frequent terms, we can avoid elongated vectors and efficiently use the BoW model. We ended with a vector of length 3464.

<ins>Term Frequency-Inverse Document Frequency (TF-IDF):</ins><br>
Although the uniqueness aspect of this method is not as applicable to our data, we found it to be a fitting complement to our BoW model and the removal of stopwords only enhances its application.

## Techniques
We utilized 1 supervised + 1 unsupervised learning technique to train our model throughout the project.

#### K-Nearest Neighbors (KNN) (Supervised Technique):
Our model performs better at identifying positive reviews (Class 1) with a higher recall of 0.93 in comparison to negative reviews (Class 0) with a lower recall of 0.30. This indicates that the model is more effective at detecting positive sentiments than negative ones. Our overall accuracy is 67.16%, which is decent. For our F1-score, we are aiming for a value of 1, but instead received values of 0.42 and 0.77, which are not too poor. The imbalance in class support could be impacting the performance, since support is the number of actual occurrences of the classes, we can see that there is a disproportionate amount of positive reviews (greater amount) in comparison to negative reviews (lesser amount).

#### K-Means Clustering (Unsupervised Technique):

<ins>Elbow Method:</ins><br>
In order to determine the optimal number of clusters for K-Means Clustering, we created a function and utilized the elbow method. We coded it to calculate the sum of squares within clusters (given a range of potential cluster counts, which we set as 10) and plot a visual based off of the results. From our visual, we can see that the greatest difference, or the "elbow", appears to be around 4, 5, or 6 clusters. We ultimately settled with 4 clusters.



## Analysis

## Acknowledgements
Credit for [data](https://nijianmo.github.io/amazon/): Jianmo Ni, UCSD

**Justifying recommendations using distantly-labeled reviews and fined-grained aspects**<br>
Jianmo Ni, Jiacheng Li, Julian McAuley<br>
*Empirical Methods in Natural Language Processing (EMNLP), 2019*
