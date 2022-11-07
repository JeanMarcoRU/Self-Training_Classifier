# Self-Training Classifier: How to Make Any Algorithm Behave Like a Semi-Supervised One

An easy Python implementation of Self-Training using standard classification algorithms from the Sklearn library

![1_KqCqbiISCtMX110oTFctlA](https://user-images.githubusercontent.com/15478613/200213838-976cefa5-336f-438a-8166-31016e6259bb.gif)

## How does Self-Training work?
You may think that Self-Training involves some magic or uses a highly complex approach. In reality, though, the idea behind Self-Training is very straightforward and can be explained by the following steps:

* First, we gather all labeled and unlabeled data, but we only use labeled observations to train our first supervised model.
* Then we use this model to predict the class of unlabeled data.
* In the third step, we select observations that satisfy our predefined criteria (e.g., prediction probability is >90% or belongs to the top 10 of observations with the highest prediction probabilities) and combine these pseudo-labels with labeled data.
* We repeat the process by training a new supervised model using observations with labels and pseudo-labels. Then we make predictions again and add newly selected observations into the pseudo-labeled pool.
* We iterate through these steps until we finish labeling all the data, no additional unlabeled observations satisfy our pseudo-labeling criteria, or we reach the specified max number of iterations.

## How to use Self-Training in Python?
Let’s now work through a Python example using Self-Training Classifier on real-life data.

See example in Self-Training_Classifier.ipynb
