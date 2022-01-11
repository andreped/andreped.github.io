---
layout: post
title:  setting up multi-cuda environments
date: 2022-01-08 16:30:00
description: a quick tutorial on how to setup multiple CUDA versions on the same Linux machine and toggle between them.
tags: CUDA PyTorch TensorFlow
categories: machine-learning environments
comments: true
---


## Motivation
Working with machine learning generally requires that you have access to a dedicated GPU to enable enable rapid training and inference of models. Either if you are using TensorFlow, PyTorch, or any other framework, you will find that the library has dependencies, and often specific versions.

For instance, if you wish to use [this](https://github.com/andreped/PLS-Net) implementation of the PLS-Net architecture, it requires PyTorch 1.3.0. It might work with more recent version of PyTorch, but there are no guarantees. This is annoying, as you might be using a more recent version of PyTorch in other projects. Luckily, using different versions (and libraries) for specific applications can easily be done by creating separate virtual environments, like so:

```
$ pip install virtualenv
$ virtualenv -ppython3 venv --clear
$ source venv/bin/activate  # on UNIX
or 
$ ./venv/Scripts/activate  # on Windows
```

However, when you try to setup PyTorch or TensorFlow you realize that the framework fails to find any GPUs. This might be because the version you are using is incompatible with the CUDA and/or cudNN versions you have on your machine. Using a specific version of a library requires a very specific set of dependencies, and not just to CUDA (more information regarding dependencies can be found [here](https://www.tensorflow.org/install/source#gpu)).

Therefore, if you wish to use PyTorch 1.3.1, it might require you to use CUDA 10.0, but sadly, it is not compatible with the CUDA 11.1 version your PyTorch 1.7.0 requires. 

However, note that multiple versions of PyTorch/TensorFlow might be compatible with multiple CUDA versions. Therefore, try that first before trying any of the suggested solutions below! A compatility chart for TensorFlow-CUDA can be found [here](https://www.tensorflow.org/install/source#gpu).

## Alternative solutions
A simple solution to this can be to build PyTorch from scratch with the CUDA version you have, and that might work in many cases. However, in general, building libraries from scratch is a tedious process and might require you to make quite a bit of effort to get it to work. So for all us `pip install torch` people out there, we prefer to avoid this.

Therefore, not only do you need to create a virtual environment, but you also need to have a specific CUDA version with that environment. That is **not** possible to do using only virtualenv, as the CUDA version is (most commonly) set globally on your machine and not inside the virtual environment. 

Creating a docker image that has that specific CUDA version preinstalled is an alternative, and perhaps the preferred solution. However, there is a lot of ML developers that are not experienced with docker or know how to set it up (to be discussed in a future blog post maybe?), and it requires a lot more work than the basic virtualenv solution.

## The solution
Therefore, the solution might be to have multiple CUDA version on the same device and simply toggle between them for each session, depending on which CUDA version you need at a given time.

A good tutorial for how to do this is found [here](https://www.pugetsystems.com/labs/hpc/How-to-install-CUDA-9-2-on-Ubuntu-18-04-1184/) for CUDA 10.0 and CUDA 9.2 (on Ubuntu Linux 18.04). But the most important parts, which I struggled with when trying to setup multi-CUDA environments myself were the following steps:

* Make a file called "cuda9.2-env" and add the following:
```
> export PATH=$PATH:/usr/local/cuda-9.2/bin
> export CUDADIR=/usr/local/cuda-9.2
> export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-9.2/lib64
```

* Then to switch between the specified CUDA version, run:
```
> source path_to_file/cuda9.2-env
```

For different CUDA versions simply make different "cudaX.Y-env" files.

That's it! Now it is possible to use different CUDA version on the same platform.

What is essentially done here is that you set which CUDA version is used in the environmental variables, and therefore, PyTorch/TensorFlow is able to find the CUDA version you want to use, because it uses the environmental variables when creating the session.

But of course, for all you lazy people that want an even easier solution, simply make an alias to make toggling between these more easily. For example:
```
> alias cuda9.2-env="source /home/username/cuda_environments/cuda9.2-env"
> alias cuda10.0-env="source /home/username/cuda_environments/cuda10-0-env"
```

## Concluding remarks
And that's it. No magic really. I have done this for multiple projects with no real issue. But if you have some experience with docker, or are interesting in learning about it, I would recommend doing that instead, as docker images not only handled dependencies relevant for training, but it makes **deployment** of trained models and implemented solutions directly available on new devices and across operating systems!

I hope you found this helpful :]