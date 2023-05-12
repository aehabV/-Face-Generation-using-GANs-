# Face Generation using GANs

In this project, a Deep Convolutional Generative Adversarial Network (DCGAN) is defined and trained on the CelebFaces Attributes Dataset (CelebA) to generate new images of faces that look as realistic as possible.

## Get the Data

The CelebA dataset contains over 200,000 celebrity images with annotations. Since we're going to be generating faces, we won't need the annotations, we'll only need the images. Note that these are color images with 3 color channels (RGB) each.

## Define the Model

A GAN is comprised of two adversarial networks, a discriminator and a generator. The discriminator is a convolutional classifier that takes 32x32x3 tensor images as input and outputs a single value that indicates whether a given image is real or fake. The generator upsamples an input and generates a new image of the same size as our training data (32x32x3).

## Initialize the Weights of Networks

To help the models converge, the weights of the convolutional and linear layers in the model are initialized from a zero-centered Normal distribution with a standard deviation of 0.02.

## Training

Training involves alternating between training the discriminator and the generator. The functions `real_loss` and `fake_loss` are used to calculate the discriminator losses. The discriminator is trained by alternating on real and fake images, then the generator, which tries to trick the discriminator and should have an opposing loss function.

## Saving Samples

The code includes a function to print out some loss statistics and save some generated "fake" samples.

## Improvements

The dataset is biased towards "celebrity" faces that are mostly white, and the images have a low resolution. To improve the model, training with different types of images from different sources and adding additional convolutional layers and transposed conv layers to generate images of larger sizes with high resolution could achieve better results. Optimizers and number of epochs also affect the final result.
