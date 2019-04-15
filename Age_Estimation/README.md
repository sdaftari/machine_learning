In this notebook, we train two techniques to predict the age of face images from the IMDB WIKI dataset.

1. SVM using Local Binary Pattern (LBP) Histogram features. 
This algorithm is similar in spirit to the paper Automatic age classification with LBP by Gunay et al., which was one of the state-of-the-art Computer Vision techniques for age estimation the pre-deep learning era. 
The LBP feature is essentially a texture descriptor that encodes the regional texture at every point in the image by comparing the intensity of that pixel to 8 sorrounding pixels and generating a binary bit corresponding to that comparison. Thus we get 8 bits for the 8 neighbors and an 8 bit value LBP for each pixel. The reason why LBP features became so popular in the 2000s was becuase they are invariant to lighting changes.
Once an LBP feature is computed on an image, we then compute a histogram of each 28x28 block in the LBP image and append all the histograms of the individual blocks to create our 1024 dimensional feature vector.
Then we train an SVM using RBF Kernel to predict the age given this LBP histogram feature by performing Support Vector Regression.
We show that we can do PCA to reduce almost 50% of features from the LBP histogram without losing much variance in the input data and not losing any accuracy at all, while producing much compact Support Vectors.

2. Convolutional Neural Network Learning using MobileNet - 
We also train a MobileNet in Keras with weights pre-trained on the ImageNet dataset. 

You can see that the Deep Learning solution achieves a lower mean absolute error than the classical solution using LBP features and SVM