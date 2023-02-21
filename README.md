# Celebrity-recognition-model

Introduction
Problem
	The face recognition of celebrities is the classification task in machine learning. The application of recognition of stars can be found in the identification of real stars against double people who mostly look identical to a real celebrity, but for a computer, it can be established that they are different people.


Literature review
For this project we made some research and decided to use these documents:
A systematic study of the class imbalance problem in convolutional neural networks https://arxiv.org/abs/1710.05381 
Striving for Simplicity: The All Convolutional Net https://arxiv.org/abs/1412.6806 


Current Work
Star by Face (https://starbyface.com/) - a website that can identify the celebrity by an uploaded photo by a user.


Data and Methods
Information about the data

For the development of a model we will use the dataset from sklearn.datasets.fetch_lfw_people called Labelled Faces in the Wild, which we distributed the data by the following:

Number of examples: 3023
The dimensionality of images: (154, 154, 3)
number of unique classes (people): 62


To avoid overfitting we used a data augmentation technique where we used the following methods to reshape the pictures to train the model. 




This snippet shows how an image is translated to an understandable format for a model for further prediction. It is not clearly seen, but 

Machine Learning Models with description
The main Deep Learning model in our project is a Convolutional Neural Network with the following structure:



Our model consists of 9 layers. The first 6 of which are convolutional layers with filters from 12 to 24, (2, 2) core size and steps in every second convolutional layer. After that, we drop out 50% of all neurons to prevent overtraining. Then, we add the last convolutional layer to match the number of classes available.
In total, we have 11.066 parameters that our model will use for the recognition of celebrities.









Results
Implementation and observations

The highest accuracy achieved in epoch 150 is 74%, and the average accuracy in the test is 58.1%

This graph shows the development of accuracy during each epochs of train and test sets.

This graph shows the average accuracy of each target name. The model mostly predicted target names with more than 70% accuracy, but there are names that the model could not predict. 

The confusion matrix shows the relationship between true labelled and predicted values. It can be seen that the classification of celebrity models has been a tough task for our model. We calculated that the recall and precision of our models are 60%. 



Discussion
Critical view of results
	The average accuracy of the model shows that there is needed further development of the model even after the completion of 150 epochs. In industrial use cases, the model can make mistakes by misunderstanding the given photo of a celebrity which can cause trouble. Therefore, there is a need to improve the model. However, by using the free Google Colab sources we can not develop it more due to restrictions of RAM memory and GPU power, otherwise, the development will take more time due to the limit of powers.



Next steps for future

There are some steps to improve our model:
Add more layers with additional strides and padding 
Increase the number of examples in the dataset or use a different dataset
Increase the batch size after increasing the power of the machine
Implement the model in website or app
