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
   1. Run all cells in 'CS105 Final Project.ipynb' (for simplicity, the code has been compiled into a single cell)
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
   6. Wrote all changes to _cleaned_reviews_file_
         - Wrote to new files with each step, but final file that we input to the model is _cleaned_reviews_file_

## Data Preprocessing
We limited the size of the dataset (originally 10,000,000+ observations) to 1,000 observations in order to run the models locally

## Data Processing
#### Text Representation


## Techniques
We utilized 1 supervised + 1 unsupervised learning technique to train our model throughout the project.

#### K-Nearest Neighbors (Supervised Technique):

#### K-Means Clustering (Unsupervised Technique):

## Analysis

## Acknowledgements
Credit for [data](https://nijianmo.github.io/amazon/): Jianmo Ni, UCSD

**Justifying recommendations using distantly-labeled reviews and fined-grained aspects**<br>
Jianmo Ni, Jiacheng Li, Julian McAuley<br>
*Empirical Methods in Natural Language Processing (EMNLP), 2019*
