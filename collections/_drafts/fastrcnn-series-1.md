---
layout: post
title:  "MaskRCNN benchmark series 1/n"
categories: #[blog, travel]
tags: [research, computer vision]
# d3: True
---

This is a series of posts that will cover the [maskrcnn_benchmark](https://github.com/facebookresearch/maskrcnn-benchmark) structure and usage

![preview of maskrcnn on some custom photo](/assets/images/maskrcnn/???)

<!--more-->

# History 

<!-- ![repository statistics](/assets/images/maskrcnn/maskrcnn_repo_stats.png) -->

This project is meant as a successor of [Detectron]() 

It is written in PyTorch 1.0 and implements building blocks for detection and segmentation models.
One of the ideas is too keep the codebase readable. There are even some [pullrequests]() that suppose to improve performance but not they are not merged to master in order to keep readability

It is not only **faster** during training, but uses ~roughly 500MB less GPU~ than [mmdetection]()

More details can be found in [README.md](https://github.com/facebookresearch/maskrcnn-benchmark/blob/master/README.md)

# Structure of the project

1. configs  - directory with `yaml` config files. They give a good first understanding of what kind of parameters you can use. But many configs use a lot of default values, that can be found in the code of [defaults](https://github.com/facebookresearch/maskrcnn-benchmark/blob/master/maskrcnn_benchmark/config/defaults.py) 

we will look at all parameters closely in the consequent posts. [link to next post / or to the serie of posts]()

2. demo - Taking a first glance at this repo, we are mostly interested in this directory with scripts and notebooks that provide example of usage
3. docker - contains docker files for 2 types of containers: 1) basic  2) with jupyter
4. maskrcnn_benchmark - main codebase
5. tools - contains the train/test runner scripts that are used to train from scratch and evaluate.


# Usage on premise 



# Aws example

How to install manually

Installation with docker 

Run code 

Some performance metrics table 

| Model | Instance | fps |
| ----- | -------- | --- |
| c     | b        | XXX |


## Exmaple

[image of maskrcnn example]()

## Web server


## How to demonstrate your demo ?


To make a simle demo accessible online without spending time on configuring aws or other instance and even without buying a domain name, in other workds without any additional configuration except your dev environment is [ngrok]()

With user-friendly oneliner you can create  HTTP tunnel to your service or jupyter to make a demonstration of your POC


If you tried this repo the first time don't hesitate to ask questions and leave a feedback if some steps were not clear.

If you are already using maskrcnn_benchmark don't hesitate to ask general questions or about particular part. 
In consequence episodes we will be able to go down to explain code even line by line if necessary.


# Links

@misc{massa2018mrcnn,
author = {Massa, Francisco and Girshick, Ross},
title = {{maskrcnn-benchmark: Fast, modular reference implementation of Instance Segmentation and Object Detection algorithms in PyTorch}},
year = {2018},
howpublished = {\url{https://github.com/facebookresearch/maskrcnn-benchmark}},
note = {Accessed: [Insert date here]}
}