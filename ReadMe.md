AYTEKİN YILDIZHAN

Huawei R&D Technical Interview Question on Big Data

In this assignment, there are 3 questions.
Jupyter notebook is used.

These files are;

1. First_question.ipynb

2. Second_question.ipynb
3. Second_question2.ipynb
4. Second_question3.ipynb
5. Second_question4.ipynb
6. Second_question5.ipynb

7. Third_question.ipynb

### 1. First_question.ipynb ###

We use movielens-small.db and read this database.

We extract movielens-small.db and obtain and save four .csv files.
These files are movies, links, tags and ratings.

In this code, we solve the first part.

### 2. Second_question.ipynb ###

In this code, we solve this task:

Provide an implicit feature by using any of the data from the given database.

I designed implicit feedback.

### 2. Second_question2-5.ipynb ###

-Train two individual recommender models, one by using rating (from ratings table) 
and the other one by using your designed implicit feedback.-

In this code, we try to several recommender models using rating rable.

Second_question2 -->>>> Alternating Least Squares

Second_question3 -->>>> Bayesian Personalized Ranking

Second_question4 -->>>> Logistic Matrix Factorization

Second_question5 -->>>> kNN Nearest Neighbors

###Present comparison between two models, by using essential metrics###

All of designed recommender models' results are different.

I compare kNN model between my implicit feedback model.

In Knn model, recommended movies are 296, 2959, 457, 2571, 6874, 260, 47, 1089, 2858, 593
while in implicit feedback model, recommended movies are 706 and 8552 movieID.

In Knn model, we use cosine metric.

7. ### Third_question.ipynb ###

In this code, we solve the last part of the tasks.

We create this schema using pyspark:

root

  |-- content: string (nullable = true) 
  |-- label: string (nullable = true) 
  |-- sentiment: string (nullable = true)

Then we design a tokenizer to remove stop words. 
We compare two models 'with stopword content' and 'without stop word content'.

Firstly, we downloaded the database 'aclImdb' and we have train and test sets.
Each set are 25000
Each set has neg and pos comment as a txt file.
We combine all of them (all contents) and their labels.
Then we design a csv file with 'content' column and 'label' column.
We save this model as a csv then we carry on this file. 

Our model is below:

 Layer (type)                Output Shape              Param #   
=================================================================
 embedding_1 (Embedding)     (None, 128, 100)          5000000   
                                                                 
 lstm (LSTM)                 (None, 128, 100)          80400     
                                                                 
 lstm_1 (LSTM)               (None, 100)               80400     
                                                                 
 dense_1 (Dense)             (None, 1)                 101 

As a result, we face a problem is called 'overfitting'.
To overcome this problem, we design another model, stop early training or increase the data.
