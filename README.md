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
The first simple metric will be a number of correct hits for some K:$$ \text{Hits@K} = \frac{1}{N}\sum_{i=1}^N \, [dup_i \in topK(q_i)]$$

where $q_i$ is the i-th query, $dup_i$ is its duplicate, $topK(q_i)$ is the top K elements of the ranked sentences provided by our model and the operation $[dup_i \in topK(q_i)]$ equals 1 if the condition is true and 0 otherwise (more details about this operation could be found here).

DCG@K
The second one is a simplified DCG metric:

$$ \text{DCG@K} = \frac{1}{N} \sum_{i=1}^N\frac{1}{\log_2(1+rank_{dup_i})}\cdot[rank_{dup_i} \le K] $$
where $rank_{dup_i}$ is a position of the duplicate in the sorted list of the nearest sentences for the query $q_i$. According to this metric, the model gets a higher reward for a higher position of the correct answer. If the answer does not appear in topK at all, the reward is zero.
