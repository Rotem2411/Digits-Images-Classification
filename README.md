# Digits-Images-Classification
### Deep Learning EX2


1)	Run https://www.tensorflow.org/tutorials/keras/classification . This classifier works on fashion items.
2)	Convert it to recognize digits. There is also an minst dataset for digits.
 ![image](https://user-images.githubusercontent.com/116814148/227368056-50339ebe-83b5-410a-8cb4-70d23389f176.png)

3)	Make modifications to the networks and report the train and test accuracies as you modify the networks.  You can also change the activation function.
On Digits DataSet

Having default (given) configuration:

Train results were: 		
	Test results were: 
Changing the activation function to SIGMOID, we got: 

Train: 
	Test: 
Changing the Layers from 128 to 100, and having RELU as activation function:

Train: 

Test: 	


Changing the optimizer to Adam with learning rate at 0.01
Train: 
Test: 
Changing the Layer from 128 to 20, and having RELU as activation function

Train:  

Test: 

On Fashion DataSet

Changing the activation function to SIGMOID, we got: 
Train: 
Test:
Changing layers from 128 to 20 and activation function RELU

Train: 

Test: 

4)	For each classification result, the class with the highest probability is returned. Plot a histogram of the accuracies of the test examples for correctly and incorrectly classified objects. 

   

5)	Change the test images and use the other test set (for fashion network test on the digits test dataset and vice versa). What are the accuracies of the classifiers? Here again plot histograms. How sure are the classifiers when run on the wrong type of data? 
Having fashion as training set and digits as test set

Having digits as training set and fashion as test set
 
In both cases, the classifier in mixed training and test sets can predict successfully very small number of pictures but with very high probability, and it knows with very high probability when it makes a mistake. 
6)	Given a test image for one digit and a test image for another digit generate a set of images
I(alpha) = alpha * I1 + (1-alpha) * I2 for 100 alphas between 0 and 1. Run the digit classifier on these images and plot the results both the classification and the probability of the class. What are your conclusions from that?

Some example of the whole plotting image:











The classifier is not doing too much well when it comes to something that he is not familiar with.

7)	One of the major problems in DL is to know when the classifier makes a mistake. One idea is to use post-training dropout. That is after the training generate K classifiers which are based on the trained classifier for which dopout has been applied with a certain probability p. For this you have to randomly change p percent of the weights to 0 and update the other weights as explained in the powerpoint presentation where dropout is explained. Then the confidence of the classifier will be the percent of classifiers that voted for the same result.
What you should do is take the fashion classifier, build from it 100 classifiers and see if this method works. Try this for several values of p. Produce graphical results showing the confidence of the classifier for the test examples where the classifier made a correct classification and for the test examples where the classifier made an incorrect classification. What are your conclusions from this suggested method?  Note, as far as I know there is no code for using dropout in the test step, so you will have to write it yourself. 

By having 1% precent dropout the plotting results were:

By having 3% precent dropout the plotting results were:








By having 20% precent dropout the plotting results were:
 

By having 60% precent dropout the plotting results were:








Accuracy before adding the dropout of 1% precent
Accuracy after adding the dropout of 1% precent




Accuracy before adding the dropout of 20% precent


Accuracy after adding the dropout of 20% precent

By adding dropout, we can see the value of accuracy is being decreased, the more the % of dropout the less accuracy we get. 
From analyzing the histograms, it’s clear that having more % of dropout confuses the classifier, and there is less probability that it knows when it has incorrect classi
