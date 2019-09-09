---
layout: post
author: Vincent
---

During my penultimate year of graduation at ESIEE Paris to become an engineer, I have been interned in the Audio-visual Information Processing Lab (VIP Lab) for the CAPES/COFECUB Research Program entitled Hierarchical Graph-based Analysis of Image, Video and Multimedia Data.

My research consists in studying this paper from the Visual Geometry Group of the University of Oxford :

> Lu, Erika et al. "Class-agnostic counting." Asian Conference on Computer Vision. Springer, Cham, 2018.

[Link to the paper](https://arxiv.org/abs/1811.00472)

[Link to the project web page](http://www.robots.ox.ac.uk/~vgg/research/class-agnostic-counting/)

[Link to the Github repo](https://github.com/erikalu/class-agnostic-counting)

I have tested this new approach on other crowd datasets ([UCF-CC-50](https://www.crcv.ucf.edu/data/ucf-cc-50/) and [UCF-QNRF](https://www.crcv.ucf.edu/data/ucf-qnrf/)). The Neural Network is build with Keras on a TensorFlow backend.

___

# Table of Contents
1. [Motivation](#motivation)
2. [Approaches](#approaches)
3. [Datasets](#datasets)
4. [Generating dot annotated images](#generating-dot-annotated-images)
5. [The network](#the-network)


### Motivation

Crowd counting and crowd analysis has significant importance from safety perspective.

<!--![counting people](/img/counting-people.png)-->
<img src="/img/counting-people.png" alt="counting people" style="
    margin-right: 20%;
    margin-left: 20%;
    width: 60%;
">

### Approaches

To estimate the number of people in an image there are two main approaches : detection-based method and regression-based method.

#### Detection-based counting
<!--Detector-->

A visual object detector slides along the image to detect object instances in an image like human faces.

<!--![detection-based counting](/img/detection.png)-->
<img src="/img/detection.png" alt="detection-based counting" style="
    margin-right: 30%;
    margin-left: 30%;
    width: 40%;
">

#### Regression-based counting
<!--Regressor-->

The network produces a scalar (number of objects) as output which is then compared to ground truth.

<!--![regression-based counting](/img/regression.png)-->
<img src="/img/regression.png" alt="regression-based counting" style="
    margin-right: 30%;
    margin-left: 30%;
    width: 40%;
">

<!--### Experiments-->

### Datasets

I used these two datasets :

- [UCF-CC-50](https://www.crcv.ucf.edu/data/ucf-cc-50/)
- [UCF-QNRF](https://www.crcv.ucf.edu/data/ucf-qnrf/)

![datasets](/img/datasets.png)

### Generating dot annotated images

The program takes dot-annotated files as inputs.

The **UCF-CC-50** dataset comes with an image and its _.mat_ associated file. This _.mat_ file contains the location of every person's head. In order to generate these dot-annotated files I wrote a simple program that generates an image of points taking the position (x, y) of the heads.

![dot-annotated-img](/img/dot-annotated-img.png)

<!--![dot-img](/img/dot-img.png)-->
<img src="/img/dot-img.png" alt="dot-img" style="
    margin-right: 30%;
    margin-left: 30%;
    width: 40%;
">

#### Issues with the dataset

Generating the dot annotated files in order to produce the ground truth can be a tricky task. As you can see on the image below, some of the locations are wrong. The _.mat_ file associated to the image should locate every person's head. Some locations are approximative (shirt instead of head), others are does not locate the person and even worse some points are out of the image itself !

<!--![issues-dots](/img/issues-dots.png)-->
<img src="/img/issues-dots.png" alt="issues-dots" style="
    margin-right: 20%;
    margin-left: 20%;
    width: 60%;
">

### The basics

<span style="text-decoration:underline">During the training part </span> : The original image **I** is mapped into an dot annotated image : the **ground truth**. At this step we do not use the neural network, only image processing. The same image **I** feeds the neural network to make a **prediction** that approximates the **ground truth**. The difference or delta between the **ground truth** and the **prediction** represents the prediction error. The weights of the DNN (deep neural network) are updated during this step.

<span style="text-decoration:underline">During the testing part </span> : an another image is feed into the DNN (using the previous weights) to produce a prediction. We compare the ground truth of this image with the prediction to compute the loss.

![schematic](/img/schematic.png)

### The network

The network consists of three modules :

1. embedding
2. matching
3. adapting

![network](/img/network.png)

In the **embedding module**, the exemplar image patch and the full-resolution image are encoded into a feature vector and a dense feature map, respectively.

In the **matching module**, we learn a discriminative classifier to densely match the exemplar patch to instances in the image.

In the **adapting module**, a fraction of the trained parameters (3% of the network size) are trained to specialize the model.


<!--#### Implementation-->

<!--#### Results-->

<!--
Intro  
Problem  
  motivation  
  description  
Approaches  
  - detector
  - regressor
  - density maps -> class agnostic / deeplearning neural network

Experiments  
  - impl <- tools / study
  - Dsets
  - results
-->
