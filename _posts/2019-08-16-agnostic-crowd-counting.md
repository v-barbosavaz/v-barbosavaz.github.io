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

### Motivation

Crowd counting and crowd analysis has significant importance from safety perspective.

![counting people](/img/counting-people.png)

### Approaches

To estimate the number of people in an image there is two principal approaches : detection-based method and regression-based method.

#### Detection-based counting
<!--Detector-->

A visual object detector slides along the image to detect object instances in an image like human faces.

![detection-based counting](/img/detection.png)

#### Regression-based counting
<!--Regressor-->

The network produces a scalar (number of objects) as output which is then compared to ground truth.

![detection-based counting](/img/regression.png)

<!--### Experiments-->

### Datasets

- [UCF-CC-50](https://www.crcv.ucf.edu/data/ucf-cc-50/)
- [UCF-QNRF](https://www.crcv.ucf.edu/data/ucf-qnrf/)

![datasets](/img/datasets.png)

### Generating dot annotated images

![dot-annotated-img](/img/dot-annotated-img.png)

![dot-img](/img/dot-img.png)

#### Issues with the dataset

![issues-dots](/img/issues-dots.png)


### The network

![network](/img/network.png)

![schematic](/img/schematic.png)

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
