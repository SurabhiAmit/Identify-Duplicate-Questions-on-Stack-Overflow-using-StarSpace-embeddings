# StarSpace_embeddings
Word2Vec embeddings and StarSpace embeddings are used to learn how to calculate a similarity for pieces of text. 
This project then shows how to find duplicate questions on StackOverflow based on sentence similarity of the questions.

## Used Libraries
StarSpace — a general-purpose model for efficient learning of entity embeddings from Facebook
Gensim — a tool for solving various NLP-related tasks (topic modeling, text representation, ...)
Numpy — a package for scientific computing.
scikit-learn — a tool for data mining and data analysis.
Nltk — a platform to work with human language data.

## Data
The required data is present inside the data folder and the code has a block that downloads this data from google collab.

## Evaluation of sentence similarity
The first simple metric will be a number of correct hits for some K. [Hits@k]
Collects the top K elements of the ranked sentences provided by our model and assigns 1 if the condition that duplicate is at position<=k and 0 otherwise.

DCG@K
The second one is a simplified DCG metric:
According to this metric, the model gets a higher reward for a higher position(rank 1) of the correct answer. If the answer does not appear in topK at all, the reward is zero.

Note: Data could not be pushed to GIT because of size restrcitions. So those files are stored in my private hard disk and will be provided as required.
