# enron-intent-classification-
Problem statement  Intent detection on Enron email set. We define "intent" here to correspond primarily to the categories "request" and "propose". In some cases, we also apply the positive label to some sentences from the "commit" category if they contain datetime, which makes them useful. Detecting the presence of intent in email is useful in many applications, e.g., machine mediation between human and email. The dataset contains parsed sentences from the email along with their intent (either 'yes' or 'no'). You need to build a learning model which detects whether a given sentence has intent or not. Its a 2-class classification problem. Although its not required you can refer this paper for more information on the dataset : Cohen, William W., Vitor R. Carvalho, and Tom M. Mitchell. "Learning to Classify Email into``Speech Acts''." EMNLP. 2004.

# Approach to solve :
so first dataset loaded as it was tab seprated dataset we use delimter

basic cleaning done using nltk remomving stopwords taking ,alphanumeric words , digits i did not remove as it was mentioned in the problem that number in text makes intent of email usefull 

then we checked the balance of classes 

wordcloud analysis for no and yes classes (see the notebook)

email lenght analysis 

TSNE Data analyis to see seprability in data 

vector conversion 1> Countvectorizer -> tfidf transformer 

new apporach tried :
1>synonymns agumnetation but semantics were changing so idea dropped 
2>Dimension Reduction PCA did not work 
3>n-GRAMS tried memory overflow with 22k features 
4>Voting classifier worked with 82.45 accuracy increased in 0.004 percent from 82.05

model used :

1> SVM 
2> Random Forest
3> Xg-boost
4> Light GBM

hybrid classifer : SVM + Random Forest + Xg-boost + Light GBM

Final accuracy on test set : 82.45

Auc score 79.46

AUC is desirable for the following two reasons:
1 AUC is scale-invariant. It measures how well predictions are ranked, rather than their absolute values.
2 AUC is classification-threshold-invariant. It measures the quality of the model's predictions irrespective of what    classification threshold is chosen.





