####### README file for Anna Lieb's CS 315 final project #######
All files listed here, in addition to full Reddit data sets, are available at (restricted access): 
https://cs.wellesley.edu/~al117/cs315-assignments/finalproject/

######### PM5 - Created on May 16, 2021  ##########
Many of the documents and code files from PM3 were not changed in PM5. A description of PM5 updates is listed below. 

Edited documents: 
common_subreddits.csv ==> added column for % of corpus that was posted in each subreddit
PM5 - Data Cleaning & Exploration.ipynb (or .html) ==> Added code to find the number of distinct subreddits in data set.

######### PM3 - Created on May 9, 2021  ##########
The jupyter notebook files with code for data analysis were created in this order: 

1. PM3 - Revised Data Collection.ipynb (or .html)
>> Description: After downloading Pushshift dumps, this code reads through the decompressed .zst file of raw Reddit data, extracts relevant posts, and writes them to an output .csv file. 
>> Generates: csv files located in the Extracted folder; titles indicate the month posted, and start with RC for comments or RS for submissions. The Extracted folder is not available here on GitHub, but it can be found at https://cs.wellesley.edu/~al117/cs315-assignments/finalproject/ for those with Wellesley permissions.
** Note that the input .zst files are not uploaded to the cs server, but can be found at https://files.pushshift.io/reddit/ 

2. PM3 - Data Cleaning & Exploration.ipynb (or .html)
>> Description: Code to learn more about the most common subreddits, most common words, and distribution of post lengths within the data set. 
>> Generates: common_subreddits.csv, common_words.csv, RC_from_topSubs.csv, RS_from_topSubs.csv, 100_random.csv, 100_random_topSubs.csv

3. PM3 - Data Analysis.ipynb (or .html)
>> Description: Application of data analysis algorithms including (1) LDA topic modeling and (2) Word2Vec word embedding
>> Generates: word-embeddings.csv

Descriptions of generated .csv files: 

Extracted (folder): csv files of raw comments and posts extracted from Pushshift repository containing data privacy keywords. Titles indicate the month posted, and start with RC for comments or RS for submissions. Fields include created_utc (UTC time the post was created), author, body (text of post for comments only) / selftest (text of post for submissions only), subreddit, id, and permalink. 

common_subreddits.csv: List of top 200 most common subreddits represented in the set of data privacy-related reddit posts, along with the number of posts belonging to each subreddit. 

common_words.csv: List of top 200 most common words in extracted reddit posts and the number of times they appear in the data set. 

RC_from_topSubs.csv: Contains all comments from the RC-prefixed csv files in the Extracted folder that belong to the top 200 subreddits listed in common_subreddits.csv.

RS_from_topSubs.csv: Contains all submissions from the RS-prefixed csv files in the Extracted folder that belong to the top 200 subreddits listed in common_subreddits.csv.

100_random.csv: Contains a list of 100 randomly-selected reddit posts from Extracted. Used to estimate the relevance of extracted posts. 

100_random_topSubs.csv: Contains a list of 100 randomly-selected reddit posts from RC_from_topSubs.csv and RS_from_topSubs.csv (ie. Comments and submissions from the 200 most common subreddits in our data set). Used to calculate the relevance of posts that come from the top 200 most common subreddits in the common_subreddits.csv file.

word-embeddings.csv: Stores output of Word2Vec word embedding model trained on extracted Reddit data for chosen key words. Output includes the top-10 most similar words to the key words, with coefficients for their similarity in context (coefficient rates from 0 to 1, with 1 being most similar). 
