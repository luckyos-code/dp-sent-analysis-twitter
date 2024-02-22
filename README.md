# Sentiment Analysis on Twitter using Differential Privacy

Sentiment analysis is a crucial tool to evaluate customer opinion on products and services. However, analyzing social media data raises concerns about privacy violations since users may share sensitive information in their posts. In this work, we propose a privacy-preserving approach for sentiment analysis on Twitter data using Differential Privacy (DP). We first implement a non-private baseline model and assess the impact of various settings and preprocessing methods. We then extend this approach with DP under multiple privacy parameters ε = {0.1, 1, 10} and finally evaluate the usability of the resulting private models. Our results show that DP models can maintain high accuracy for the studied task. We contribute to the development of privacy-preserving machine learning for customer opinion analysis and provide insights into trade-offs between privacy and utility. The proposed approach helps protect sensitive information while still allowing for valuable insights to be gained from social media data.
 
## Environment:

- Python 3.9.5
- RAM: 16GB and 32GB
- GPU: NVIDIA GeForce RTX 2070 and NVIDIA Tesla V100
 
## Dataset: https://www.kaggle.com/datasets/kazanova/sentiment140 

- ```notebooks/baseline``` contains non-private Sentiment Analysis
- ```notebooks/dp``` contains private Sentiment Analysis
- code in ```notebooks/learning rate``` is used to obtain the learning rate of the LR-Model
- code in ```notebooks/preprocessing``` is used for the preprocessing techniques and for the procedure of saving the resulting datasets to CSV files.


## How to run:

- download dataset from https://www.kaggle.com/datasets/kazanova/sentiment140
- change the encoding of the dataset to UTF-8
- run ```notebooks/preprocessing/remove_tweets.pynb``` (set TRAINDATA_PATH to the filepath of the downloaded train dataset). This creates the file ```train_tweets_removed.csv``` in ```notebooks/preprocessing/data```
- create an empty folder called ```csv_rows``` in ```notebooks/preprocessing/data```
- run ```notebooks/preprocessing/all-preprocessing.ipynb```
- run the desired experiments on the preprocessed datasets (they will be saved in ```notebooks/preprocessing/data/csv_rows```, so you might want to change the FILES_DIRECTORY variable leading inside the folder ```csv_rows```)
