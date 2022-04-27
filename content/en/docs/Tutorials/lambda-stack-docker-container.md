---
title: "How to Use Lambda Stack to Create a GPU-accelerated PyTorch Docker Container"
date: 2022-04-12
weight: 4
description: >
  This tutorial explains how to use Lambda Stack to create a GPU-accelerated PyTorch Docker container.
---

1. Install [Lambda Stack](https://lambdalabs.com/lambda-stack-deep-learning-software).
   Lambda Stack installs the NVIDIA drivers needed to run GPU-accelerated
   Docker containers. Lambda Stack also installs deep learning libraries and
   frameworks such as:

   - [TensorFlow](https://www.tensorflow.org/)
   - [PyTorch](https://pytorch.org/)
   - [Keras](https://keras.io/)

1. Install the latest version of [Docker](https://www.docker.com/) and
   [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/overview.html).
   To install the latest version of Docker and NVIDIA Container Toolkit, run
   the following command in a terminal:

   `sudo apt-get update && sudo apt-get install docker.io nvidia-container-toolkit`

1. Reboot your computer.

1. Download the NVIDIA NGC Catalog [PyTorch Docker image](https://catalog.ngc.nvidia.com/orgs/nvidia/containers/pytorch).
   To download the image, run the following command in a terminal:

   `sudo docker pull nvcr.io/nvidia/pytorch:22.03-py3`

1. You can create a directory to share with the container that you are
   creating. To do so, run the following command in a terminal:

   `mkdir $data`

   You can substitute `$data` with a directory name of your choice.

1. Create the container by running the following command in a terminal:

   `sudo docker run --gpus all -it --rm nvcr.io/nvidia/pytorch:22.03-py3`

   If you followed step 5. and created a directory to share with the container
   that you are creating, run the following command instead:

   ```
   sudo docker run --gpus all -it --rm -v `pwd`/$data:/$data \
   nvcr.io/nvidia/pytorch:22.03-py3
   ```

   Substitute `$data` with the name of the directory you created in step 5.

1. You are now running a GPU-accelerated PyTorch Docker container.

   If you created a shared directory in step 5., the directory is mounted at
   `/$data`. Substitute `$data` with the name of the directory that you
   created.

1. To exit the container, run the command `exit`.
