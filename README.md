ProblemClass-Classification
===========================

Problem Class Classification will classify the description accordingly. Right now I have 5 classification in my training set.

This engine is deployed using Docker container service. It is desinged with Flask framework so that anyone can integrate it using APIs.

Naive Bayesian Classifier
=========================
This is an implementation of a Naive Bayesian Classifier written in Python. The utility uses statistical methods to classify documents, based on the words that appear within them. A common application for this type of software is in email spam filters.

The utility must first be 'trained' using large numbers of pre-classified documents, during the training phase a database is populated with information about how often certain words appear in each type of document. Once training is complete, unclassified documents can be submitted to the classifier which will return a value between 0 and 1, indicating the probablity that the document belongs to one class of document rather than another.

Training
--------

To train the utility, replace the training file and run the following the get API:

    <server IP>:8500/train

For example my server IP is 10.114.220.111

    10.114.220.111:8500/train
    > Successfully Trained

It will return saying successfully trained. 

Classification
--------------

Once training is successful, classification is performed using the following get API:

    <server IP>:8500/problemclass/text="<description>"

+ The *text* argument is the description for which you want to get the classified result.

For example:

    10.114.220.111:8500/problemclass/text="Host is Unavailable"
    > {"Classification":"Availability","confidence":"99.7845157"}

