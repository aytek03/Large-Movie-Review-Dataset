### question.ipynb ###

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
