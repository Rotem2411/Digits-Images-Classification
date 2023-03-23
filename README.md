# Digits-Images-Classification
### Deep Learning EX2


1)	Run https://www.tensorflow.org/tutorials/keras/classification . This classifier works on fashion items.
2)	Convert it to recognize digits. There is also an minst dataset for digits.
 ![image](https://user-images.githubusercontent.com/116814148/227368056-50339ebe-83b5-410a-8cb4-70d23389f176.png)

3)	Make modifications to the networks and report the train and test accuracies as you modify the networks.  You can also change the activation function.
On Digits DataSet

Having default (given) configuration:

Train results were: ![image](https://user-images.githubusercontent.com/116814148/227368205-aa56a4bf-bb44-4844-9e8c-165e28c51693.png)
		
Test results were: ![image](https://user-images.githubusercontent.com/116814148/227368242-ae3afa0a-3fec-4191-a793-f3a91e181818.png)

Changing the activation function to SIGMOID, we got: 

Train: ![image](https://user-images.githubusercontent.com/116814148/227368267-45b98a93-977e-4982-a33f-6a33fd9dad48.png)

Test: ![image](https://user-images.githubusercontent.com/116814148/227368301-cbe56089-f495-4234-9b89-73a6d7f234c2.png)

Changing the Layers from 128 to 100, and having RELU as activation function:

Train: ![image](https://user-images.githubusercontent.com/116814148/227368350-5a7f8321-4329-4966-a1c9-fe165813f7eb.png)


Test: 	![image](https://user-images.githubusercontent.com/116814148/227368379-5b3aa07e-aa65-4f20-bdd4-e251408c61a9.png)



Changing the optimizer to Adam with learning rate at 0.01

Train: ![image](https://user-images.githubusercontent.com/116814148/227368400-a1626d04-134d-477e-b56d-d1e2b65bb1a1.png)

Test: ![image](https://user-images.githubusercontent.com/116814148/227368415-5f7fa996-e9c3-43a7-9310-bfe74682df3b.png)

Changing the Layer from 128 to 20, and having RELU as activation function

Train:  ![image](https://user-images.githubusercontent.com/116814148/227368454-cbe1c6c9-b5cf-4edd-9759-e6f7986dd772.png)


Test: ![image](https://user-images.githubusercontent.com/116814148/227368465-4feee46a-e9b1-4936-b522-fb6f0ae1a842.png)


On Fashion DataSet

Changing the activation function to SIGMOID, we got: 

Train: ![image](https://user-images.githubusercontent.com/116814148/227368495-ece45cee-4bc7-46b6-a898-4835340c75e4.png)

Test:![image](https://user-images.githubusercontent.com/116814148/227368519-a6a5bd73-43b2-4e05-a873-919c6bdc6206.png)

Changing layers from 128 to 20 and activation function RELU

Train: ![image](https://user-images.githubusercontent.com/116814148/227368563-22768773-8bfa-4e00-8d7c-f16be1f83459.png)


Test: ![image](https://user-images.githubusercontent.com/116814148/227368588-43315280-4a68-4167-acb2-b97a7a6d17cd.png)


4)	For each classification result, the class with the highest probability is returned. Plot a histogram of the accuracies of the test examples for correctly and incorrectly classified objects. 
5)	
![image](https://user-images.githubusercontent.com/116814148/227368640-40a7211f-a940-4620-8942-737d1f5f90ec.png)
![image](https://user-images.githubusercontent.com/116814148/227368653-e50bfd1e-cbc6-4b82-b4ca-a7809bc1e5cc.png)

   

5)	Change the test images and use the other test set (for fashion network test on the digits test dataset and vice versa). What are the accuracies of the classifiers? Here again plot histograms. How sure are the classifiers when run on the wrong type of data? 
Having fashion as training set and digits as test set

 ![image](https://user-images.githubusercontent.com/116814148/227368695-503a63a4-24d1-41ff-b6b7-1a2f065b33c8.png)
![image](https://user-images.githubusercontent.com/116814148/227368711-db2513a3-0394-4df0-8b4e-b49949f72ece.png)

Having digits as training set and fashion as test set
 
![image](https://user-images.githubusercontent.com/116814148/227368746-c347d201-c39d-4de0-be84-d6a8c199abc4.png)
![image](https://user-images.githubusercontent.com/116814148/227368776-b5b2f431-9c6a-410d-bcce-c958f6ae8837.png)

In both cases, the classifier in mixed training and test sets can predict successfully very small number of pictures but with very high probability, and it knows with very high probability when it makes a mistake. 
6)	Given a test image for one digit and a test image for another digit generate a set of images
I(alpha) = alpha * I1 + (1-alpha) * I2 for 100 alphas between 0 and 1. Run the digit classifier on these images and plot the results both the classification and the probability of the class. What are your conclusions from that?

Some example of the whole plotting image:

![image](https://user-images.githubusercontent.com/116814148/227368865-b837d361-430c-487c-917a-dd19eb9edc2c.png)
![image](https://user-images.githubusercontent.com/116814148/227368883-1b21c43e-f115-4fcc-800d-d165143978ad.png)
![image](https://user-images.githubusercontent.com/116814148/227368899-225385fc-1548-4154-b9ad-f9834c907afb.png)










The classifier is not doing too much well when it comes to something that he is not familiar with.

7)	One of the major problems in DL is to know when the classifier makes a mistake. One idea is to use post-training dropout. That is after the training generate K classifiers which are based on the trained classifier for which dopout has been applied with a certain probability p. For this you have to randomly change p percent of the weights to 0 and update the other weights as explained in the powerpoint presentation where dropout is explained. Then the confidence of the classifier will be the percent of classifiers that voted for the same result.
What you should do is take the fashion classifier, build from it 100 classifiers and see if this method works. Try this for several values of p. Produce graphical results showing the confidence of the classifier for the test examples where the classifier made a correct classification and for the test examples where the classifier made an incorrect classification. What are your conclusions from this suggested method?  Note, as far as I know there is no code for using dropout in the test step, so you will have to write it yourself. 

By having 1% precent dropout the plotting results were:

![image](https://user-images.githubusercontent.com/116814148/227368922-d9eb9635-405f-43c2-849b-62a82032245d.png)
![image](https://user-images.githubusercontent.com/116814148/227368931-0a1c238c-4553-4841-aca4-e01abff0d09d.png)

By having 3% precent dropout the plotting results were:

![image](https://user-images.githubusercontent.com/116814148/227368953-49d54b9a-5233-4db0-93ac-253e961e107d.png)
![image](https://user-images.githubusercontent.com/116814148/227368969-6a69862b-e361-4ff4-8262-de004fc27ede.png)

By having 20% precent dropout the plotting results were:
 
![image](https://user-images.githubusercontent.com/116814148/227369034-8c3450fc-3944-46a5-aa1b-9ef6949e092e.png)
![image](https://user-images.githubusercontent.com/116814148/227369044-84897b82-bf17-469d-a6b7-eec2b47354de.png)

By having 60% precent dropout the plotting results were:

![image](https://user-images.githubusercontent.com/116814148/227369058-e6b11dea-8258-4024-b7f6-e4cf1e4e6d76.png)
![image](https://user-images.githubusercontent.com/116814148/227369080-c6401085-27b4-47f1-a044-0b30588ced2c.png)

Accuracy before adding the dropout of 1% precent

![image](https://user-images.githubusercontent.com/116814148/227369112-e530b62e-63be-4909-a2de-f081450283b1.png)

Accuracy after adding the dropout of 1% precent

![image](https://user-images.githubusercontent.com/116814148/227369153-23287a6b-1e79-4941-9184-571aac44d005.png)

Accuracy before adding the dropout of 20% precent

![image](https://user-images.githubusercontent.com/116814148/227369176-25fb5864-0f19-4630-bd5c-c1edbfc2a826.png)

Accuracy after adding the dropout of 20% precent

![image](https://user-images.githubusercontent.com/116814148/227369222-06db74b9-b802-40a9-b61a-e0e259cb6f91.png)

By adding dropout, we can see the value of accuracy is being decreased, the more the % of dropout the less accuracy we get. 
From analyzing the histograms, it’s clear that having more % of dropout confuses the classifier, and there is less probability that it knows when it has incorrect classi
