# deep-learning-augmented-xray-classification
_Notebooks created to determine if data augmentation improves chest x-ray classification_

Paper is WIP

This repository contains the following notebooks:

__GAN__: This is a generative adversarial network utilizing the Adam optimizer. It takes in 128x128x1 Tensors (128x128px single-channel images) and trains the generator and disriminator. This is used to generate augmented images of chest x-ray scans which we use to see if it improves a convolutional neural network  in identifying whether a patient has pneumonia.

__CNN__: This is a convolutional neural network trained against the original and augmented dataset to properly identify if a patient has pneumonia and whether or not it is bacterial or viral through multiclass classification. 

The CNN uses transfer learning from the ResNeXt-50 (32x4d) model with an Adam optimizer. The initial 1D convolution layer within ResNeXt-50 (32x4d) is adjusted to accept tensors from single-channel images

References / Learning Resources:
[1] https://pytorch.org/tutorials/beginner/dcgan_faces_tutorial.html
[2] https://towardsdatascience.com/getting-started-with-gans-using-pytorch-78e7c22a14a5
[3] https://www.pluralsight.com/guides/introduction-to-resnet