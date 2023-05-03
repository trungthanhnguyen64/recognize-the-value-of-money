# Recognize the value of money
The task of the problem is: when we put money into the camera, the system must recognize the denomination of each note.
To do the math, we need to go through the following steps.

   Part 1 – Problem Analysis

The proposed implementation will include the following steps:
+ Generate data by reading photos of banknotes from the camera
+ Design a NN with an image input (128,128,3), put it into the VGG16 network and the output of VGG16 will be used to put into a small NN ending with a Dense layer and softmax function.
+ The output will be a softmax vector containing p(i) probabilities for each class i, we will print the max value in that vector and choose that as the prediction class.

   Part 2 – Creating data for the problem
The simple way to create data is to write a python script that reads continuously from the camera and saves it in the respective folders with the images of the banknotes. For example, in this article, I sampled with 3 classes of 10000,20000 and 50000 (please pay attention to edit the line label = "0000" to be the class that you want to capture data)

   Part 3 – Processing image data
+ Convert labels (which are 00000,10000,20000….) to one-hot
+ Resize the image to 128×128
+ Save and read photos

   Part 4 – Designing a CNN Classify network for training

   Part 5 – Using augmentation for data

   Part 6 – Train model CNN Classify
We will use model.fit_generator to train.

   Part 7 – Testing the CNN Classify model
Now you run the file test.py to test the model. This file is pretty simple:
+ Read photos from camera
+ Perform image resize, image normalize, convert to tensor and put into model to predict
+ Get the output and display it on the screen
