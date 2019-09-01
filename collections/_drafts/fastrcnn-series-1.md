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

The repo provides Dockerfile to run a code with/without jupyter notebook. There is a good [install](https://github.com/facebookresearch/maskrcnn-benchmark/blob/master/INSTALL.md) instruction. It is quite straight forward to install on Linux, Windows users might encounter some problems and I refer them to the github issues.

# Aws example

Let's look how to install and run the demo code from the AWS instance. 

To build docker repo we will need :
1. `g2.2xlarge` or another instance with GPU support
2. AMI with ubuntu and CUDA drivers installed
3. `nvidia-docker` or `docker >= 19.03` installed that can give to your containers access to GPU 



# install docker 19


{% highlight bash %}
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

sudo apt-get update

sudo apt-get install docker-ce
{% endhighlight %}
To be abel to user docker in usermod add current user to the `docker` group and restart terminal or reconnect by ssh.

{% highlight bash %}
sudo usermod -aG docker ubuntu
{% endhighlight %}



{% highlight bash %}
git clone https://github.com/facebookresearch/maskrcnn-benchmark
cd maskrcnn-benchmark/
{% endhighlight %}

Following temporal inconsitency between `maskrcnn_benchmark` and `torchvision` we have to make some modifications to Dockerfile as mentioned in this [issue](https://github.com/facebookresearch/maskrcnn-benchmark/issues/1056) to install `torchvision v0.3.0` 

We will build docker image with jupyter-notebook so modify `docker/docker-jupyter/Dockerfile` as in issue.


{% highlight bash %}
docker build -t maskrcnn-benchmark-jupyter docker/docker-jupyter/
{% endhighlight %}

That will take approximately `Xm Ys` 

Run jupyter-notebook with docker container using
{% highlight bash %}
docker --gpus=all run -td -p 8888:8888 -e PASSWORD=<password> -v <host-dir>:<container-dir> maskrcnn-benchmark-jupyter
{% endhighlight %}

Open `demonotebook` ... 




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


To make a simle demo accessible online without spending time and money on configuring aws or other instances and even without buying a domain name, in other workds without any additional configuration except your dev environment you can use [ngrok](https://dashboard.ngrok.com/get-started)

With user-friendly oneliner you can create  HTTP tunnel to your service or jupyter notebook to make a demonstration of your POC.

1. Sign up on ngrok site 
2. Download ngrok for you architecture
3. Unzip to get an executable
4. Connect to ngrok with `./ngrok authtoken ...`
5. Use `./ngrok http PORT` 
   
P.S.:
* don't forget to change a region to the closest to you with `--region `
* you can also add `password` to secure your connection


# Conclusion

In this post we covered the high level structure of maskrcnn_benchmark repository and gave the examples of how to use it.
In the next posts we will examine the codebase of the model and explain the implemetation of different parts of detection and segmentation pipelines.

If you tried this repo the first time don't hesitate to ask questions and leave a feedback if some steps were not clear.

If you are already using maskrcnn_benchmark don't hesitate to ask general questions or about particular part. 
In the following episodes we will be able to go down to the details explaining code line by line if necessary.


# Links

@misc{massa2018mrcnn,
author = {Massa, Francisco and Girshick, Ross},
title = {{maskrcnn-benchmark: Fast, modular reference implementation of Instance Segmentation and Object Detection algorithms in PyTorch}},
year = {2018},
howpublished = {\url{https://github.com/facebookresearch/maskrcnn-benchmark}},
note = {Accessed: [Insert date here]}
}