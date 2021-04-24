# deep-learning-augmented-xray-classification
_This repo contains Jupyter notebooks that I created while working on a group paper to determine if data augmentation improves chest x-ray classification_

Paper is WIP

### Problem:
In some cases, it isn't possible to gather enough data to train one's models on can. For example, the medical field is required to keep data private (HIPPA), so gathering x-ray scans could prove difficult. In the paper we look at different approaches and the results of each approach within the scope of medical scans.

[View chest-xray-pneumonia Dataset](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia)

### This repository contains the following notebooks:

__CNN__: This is a convolutional neural network trained against the original and augmented dataset to properly identify if a patient has pneumonia and whether or not it is bacterial or viral through multiclass classification. 

The CNN uses transfer learning from the ResNeXt-50 (32x4d) model with an Adam optimizer. The initial 1D convolution layer within ResNeXt-50 (32x4d) is adjusted to accept tensors from single-channel images


__GAN__: This is a generative adversarial network utilizing the Adam optimizer. It takes in 128x128x1 Tensors (128x128px single-channel images) and trains the generator and disriminator. This is used to generate augmented images of chest x-ray scans which we use to see if it improves a convolutional neural network  in identifying whether a patient has pneumonia.


__Transformation__: This is a simple notebook that applies simple transformations to the original dataset. This will be used to help prevent overfitting and promote generalization. 

### Tools / Frameworks

[Google Colab](https://colab.research.google.com/): This is incredibly affordable ($10/mo for 3 concurrent instances of Tesla P100 gpus). Google Drive can be mounted to circumvent the ephemeral storage. Additionally, Google's custom notebook software allows input into cli prompts.

[Weight & Biases](https://wandb.ai/): Used to log and track runs.

[PyTorch](https://pytorch.org/)

[Torchvision](https://pytorch.org/vision/stable/index.html)

### References / Learning Resources:
[1] https://pytorch.org/tutorials/beginner/dcgan_faces_tutorial.html
[2] https://towardsdatascience.com/getting-started-with-gans-using-pytorch-78e7c22a14a5
[3] https://www.pluralsight.com/guides/introduction-to-resnet
