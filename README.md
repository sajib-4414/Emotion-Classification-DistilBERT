# Emotion-Classification-DistilBERT
This project was created for the data science course. DisTilBERT is a lightweight version of BERT model. BERT was a transfer learning Natural language processing model
proposed in 2018. Since then it has been used for numerous tasks such as classification, regression. BERT has been pretrained with millions of data from the Wikipedia to 
understand langauge. DistilBERT still has a good performance reducing some features from BERT for decreasing the learning time.

I have used pre-trained DistilBERT model [2] and softmax activation function. Softmax activation function is used to use DistilBERT for multiclass classification. The data is taken from Lukas's repository [3]. The ktrain library is used as a wrapper for softmax function and tokenizing functions.
### Brief description
- Data format: data is in a CSV format. It has 5 emotion labels, ```joy, sadness, fear, anger, neutral```
- Data is first tokenized using the tokenizer method for distilbert, it is implemented in the ktrain library.  
- Then test and train variable is defined with the labels given. If you want to use this code for any other dataset, change the labels in the ```encoding``` variable.
- Then ktrain's text classifier is invoked which uses softmax. DistilBERT is specified as a model and ktrain preprocesses the data as DistilBERT needs.
- With batch size 6, learner is declared with the classifier model. Then the learner is trained with epoch 4
- Then the validator method is run to check precision and recall against the test data. Class labels are given as parameters. 
- From this learner, we get the predictor finally, and save it. We can also see the predictor classes. 

##### Additional information:
- To reduce training time, in this code, only 1000 data from the dataset has been taken for training. It can be changed by modifying the sizes in the
```X_train, y_train``` variable declarations
- This code assumes the data is in the CSV format and follows the exact pattern which is found in the train and test data. If you want to use it for any other purpose, process 
the data. 
- My google drive storage was used to access the dataset and save the model. Have to change the data source as needed when using this code. 

#### References
[1] Devlin, J., Chang, M. W., Lee, K., & Toutanova, K. (2018). Bert: Pre-training of deep bidirectional transformers for language understanding. arXiv preprint 
arXiv:1810.04805.

[2] Sanh, V., Debut, L., Chaumond, J., & Wolf, T. (2019). DistilBERT, a distilled version of BERT: smaller, faster, cheaper and lighter. arXiv preprint arXiv:1910.01108.

[3] https://github.com/lukasgarbas/nlp-text-emotion
