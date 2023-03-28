# Facial Recognition using Eigenfaces
This repository contains code for a problem related to face recognition in pattern recognition. The problem involves performing Principal Component Analysis(PCA) and extracting eigenfaces for recognition goal. 

## Course Information

This problem is related to a *Statistical Pattern Recognition* course taught by Professor Mohammad Rahmati (<rahmati@aut.ac.ir>) in the Computer Engineering department at Amirkabir University of Technology (AUT) in Tehran, Iran. The course was offered in the Fall of 2021.

## Problem Description
Matthew Turk and Alex Pentland were the pioneers who applied Principal Component Analysis (PCA) to the issue of facial recognition. Their approach, known as Eigenfaces and presented in 1991, is regarded as the first successful facial recognition algorithm.

The goal of this problem was to implement Eigenfaces to tackle the problem of facial recognition using the LFW dataset, which contains natural face images. The provided subset comprises 894 cropped and grayscale images of size 80×60, representing 73 distinct individuals. Let's see how the Eigenfaces algorithm performed on this dataset.

a. The function eigenfaces_train(trainset,v) was implemented, which takes an n×d train set images matrix trainset (where n = 821 is the number of training images, and d = 4800 is the number of pixels in each image), performs Principal Component Analysis on the data, and computes the top v eigenvectors. It returns the v×d matrix of eigenvectors W and a d-dimensional vector mu representing the mean of the training faces. The top 50 eigenvectors were computed.

b. Each of the top 50 eigenvectors obtained in the previous part was reshaped, and they were displayed by appending them together into an 800×300 image (a grid of images containing 5 rows and 10 columns).

c. 10 random images from the train set were selected, and the reconstruction of each of these images using only the top v eigenvectors (where v = 1,…,10) was displayed. This reconstruction procedure projected each image into a v-dimensional space, projected that v-dimensional space back into a 4800 dimensional space, and finally reshaped that 4800 vector into an 80×60 image.

d. The Eigenfaces method's performance was evaluated by implementing a function with the header testset_labels=eigenfaces_test(trainset,trainlabels,testset,W,mu,v). This function took the train set matrix trainset and their labels vector trainlabels, the test set matrix testset, and the outputs of PCA, W, and mu, and the number of eigenvectors to use v. It first projected each image from trainset and testset onto the space spanned by the first v eigenvectors. Then it classified each test image using the nearest neighbor (1-NN) classifier by considering L2 distance in the lower dimensional space. It returned an m-dimensional vector testset_labels encoding the predicted class label for each test face, where m = 40 is the number of test images. eigenfaces_test was evaluated on the test set images for values v = 1,…,50, and the error rates were plotted as a function of v.

e. The previous part was repeated, but the first 5 eigenvectors were thrown away. In other words, v eigenvectors starting with the 6th eigenvector were used. A plot similar to the one in the previous step was produced, and the result was commented on. The difference in recognition performance compared to the previous part was explained.

![Output](/output.png)


## Repository Contents

The repository contains Python code for the problem described above, as well as a Jupyter notebook that explains the problem and provides a step-by-step cells for running the code.

## Feedback

If you have any feedback or suggestions for improving this code, please feel free to open an issue in the repository as well as send an email to Mohsen Ebadpour (<m.ebadpour@aut.ac.ir> , <mohsenebadpour@outlook.com>).



