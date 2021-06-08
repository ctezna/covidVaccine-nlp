# Covid Vaccine NLP Analysis

Steps to reproduce:

1. Go to data/ and download datasets from Kaggle (rename the Twitter Sentiment 140 dataset to twitterSentiment.csv)
2. Create a bucket in Amazon S3 that will contain the datalake. For example "docstore-datalake".
3. Inside "docstore-datalake" create 5 zones as follows:
    - 01-raw/
    - 02-preprocessed/
    - 03-processed/
    - 04-production/
    - 05-archive/
4. Inside "01-raw/", create the following folders and load the respetive datasets into each folder:
    - 01-raw/twitterSentiment/twitterSentiment.csv
    - 01-raw/vaccinationTweets/vaccination-all-tweets.csv
5. Go to notebook/, download and upload Jupyter Notebooks to Google Colab.
6. Copy AWS Credentials (aws_access_key_id, aws_secret_access_key, aws_session_token) and paste into each notebooks "Set Up" section. Also replace the name of the variable BUCKET with the name of the datalake created in step 2.
7. Run the notebooks in the following order to successfully move data through each phase of the Data Life Cycle.
    1. docstore-raw-preprocessed.ipynb
    2. docstore-preprocessed-processed.ipynb
    3. docstore-processed-production.ipynb (Remember to use GPU and to reset runtime after correct versions of libraries are installed)
    4. docstore-production.ipynb
