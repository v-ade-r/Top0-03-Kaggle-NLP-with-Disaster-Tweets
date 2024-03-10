# Top_3%-Kaggle-NLP-with-Disaster-Tweets
Code for the "Natural Language Processing with Disaster Tweets" competition on Kaggle.

Objective: Predicting whether a particular tweet is about a disaster or not, using existing open source LLMs. 

You can learn from this code how to:

1. Preprocess text data.
2. Load pretrained open source LLM model, create tokenizer and data collator.
3. Tokenize data, and prepare datasets for the model.
4. Train the model with correctly set optimizer and early_stopping callback.
5. How to evalute the model.

# Summary -----------------------------------------------------------------------------------------------------------
"""
Models:     On this code I have testes 3 models (distilbert_uncased, bert_uncased and roberta). Roberta was a clean winner.
Preprocessing:  The best results I have got using unhashed preprocessing functions.
Learning_rate:  I looped through the list of [1e-06, 2e-06, ...,9e-05] and 2e-05 was a clean winner.
Best public score for single model:     0.84155 - generated by the code above. 
Best public score for the ensemble:     0.844 - I averaged predictions of all roberta_models with different learning 
rates trained on unpreprocessed data, and also a few best ones trained on preprocessed data. Moreover I added a few 
distilbert_uncased and bert_uncased models (27 models total). It is not very computation optimal, so I didn't put it here.

Potential tasks for optimizing predictions: 
1. Polishing the character preprocessing functions. 
2. Playing out with various random_states and learning rates not only for roberta but for bert and distilbert as well. 
3. Adding a few another 'bert' models to the ensemble, bert-large (not enough ram), different roberta. 
4. Reducing number of models in ensemble, leaving only a few ones with different and strong biases to optimize 
generalization of the ensemble.
"""
