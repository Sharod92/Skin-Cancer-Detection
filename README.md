# Skin-Cancer-Detection
In cancer, there are over 200 different forms. Out of 200, melanoma is the deadliest form of skin cancer. The diagnostic procedure for melanoma starts with clinical screening, followed by dermoscopic analysis and histopathological examination. Melanoma skin cancer is highly curable if it gets identified at the early stages. The first step of Melanoma skin cancer diagnosis is to conduct a visual examination of the skin's affected area.

The aim of the project is to shorten the time taken for the dermatologiest to examine the lesion images and determine which type of cancer it is. To acieve this we have used a CNN based neural network to classify images into 9 different types of skin cancer.

#### Link to dataset - https://drive.google.com/file/d/1xLfSQUGDl8ezNNbUkpuHOYvSpTyxVhCs/view

The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). 
All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images.

![image](https://user-images.githubusercontent.com/104120966/237009281-d17a25eb-af50-410d-98f7-0ae6e9ef6324.png)

To overcome the issue of class imbalance, used a python package Augmentor (https://augmentor.readthedocs.io/en/master/) to add more samples across all classes so that none of the classes have very few samples.

### Sample images from dataset:
![image](https://user-images.githubusercontent.com/104120966/237009489-911b98fd-c3cd-4853-9dae-b4edb5ae4c24.png)


## CNN Architecture Design

Rescalling Layer - To rescale an input in the [0, 255] range to be in the [0, 1] range.

Convolutional Layer - Convolutional layers apply a convolution operation to the input, passing the result to the next layer. A convolution converts all the pixels in its receptive field into a single value. For example, if you would apply a convolution to an image, you will be decreasing the image size as well as bringing all the information in the field together into a single pixel.

Pooling Layer - Pooling layers are used to reduce the dimensions of the feature maps. Thus, it reduces the number of parameters to learn and the amount of computation performed in the network. The pooling layer summarises the features present in a region of the feature map generated by a convolution layer.

Dropout Layer - The Dropout layer randomly sets input units to 0 with a frequency of rate at each step during training time, which helps prevent overfitting.

Flatten Layer - Flattening is converting the data into a 1-dimensional array for inputting it to the next layer. We flatten the output of the convolutional layers to create a single long feature vector. And it is connected to the final classification model, which is called a fully-connected layer.

Dense Layer - The dense layer is a neural network layer that is connected deeply, which means each neuron in the dense layer receives input from all neurons of its previous layer.

Activation Function(ReLU) - The rectified linear activation function or ReLU for short is a piecewise linear function that will output the input directly if it is positive, otherwise, it will output zero.The rectified linear activation function overcomes the vanishing gradient problem, allowing models to learn faster and perform better.

Activation Function(Softmax) - The softmax function is used as the activation function in the output layer of neural network models that predict a multinomial probability distribution. The main advantage of using Softmax is the output probabilities range. The range will 0 to 1, and the sum of all the probabilities will be equal to one.

### Model Summary
![image](https://user-images.githubusercontent.com/104120966/237009579-797c272a-ee06-484e-bf73-c7fcf4467e75.png)

### Model Performance
![image](https://user-images.githubusercontent.com/104120966/237009689-0f6a38c0-e7e2-4423-97fe-ad688a435118.png)
 
### Conclusion
We have solved the overfiting problem
We can see that the training and validation accuracy are similar and decently high
We can futher tweak the model by reducing the number of neurons in the dense layers or changing the locaiton of the dropout layers to improve performance
Re-balancing the classes by using augmented data helps in improving model performance and accuracy
