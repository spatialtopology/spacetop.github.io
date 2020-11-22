---
layout: default
title: Building Containers
parent: Documentation
permalink: /doc/containers
nav_order: 4
---

# Building Containers
{: .no_toc }
{: .fs-11 }


## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---
Containers aid reproducible research, while alleviating the pain of installing programs/packages every time you're working in a new environment.

Docker and Singularity are platforms that allow you to build and execute containers.

Reasons I had to build a container:
I needed pymvpa and nilearn, which had to run on CU's cluster. This was around 2018, prior to the conda environment feature that is now enabled on Summit and Blanca. Hence, I needed a singularity container, instead of a docker container. However, converting a docker container to singularity is easy, once you have singularity on your local machine.

---


# 0. install singularity on your local machine
Please check here.
* https://singularity.lbl.gov/install-mac
* https://singularity.lbl.gov/install-linux
* https://singularity.lbl.gov/install-windows

# 1. First start off with installing vagrant
* where I've installed it: Documents/singularity-vm
* change directory into it and run the following lines
```
cd ~/Documents/singularity-vm
vagrant init singularityware/singularity-2.4
vagrant up
vagrant ssh
```

# 2. once you've logged into vagrant, we're going to build the container
using singularity...

`IMG` : name of the container
You need to set the initial size of the image (container) 8000, i.e., 8 GB

`DEF` : has the code that builds the containers

```
IMG="snaglab_pymvpa2_nilearn.img"
DEF="debian.def"
sudo rm -f $IMG
sudo singularity create -s 8000 $IMG
sudo singularity image.create -s 8000 $IMG
sudo singularity bootstrap $IMG $DEF
```

# 3. create the singularity container

copyout the container ( in local directory not virtual machine)
```
vagrant port `( in the folder where you've installed vagrant)`
```

from local dir
```
scp -P 2222 vagrant@127.0.0.1:/home/vagrant/snaglab_pymvpa2.img .
scp -P 2222 vagrant@127.0.0.1:/home/vagrant/debian.def .
scp -P 2222 vagrant@127.0.0.1:/home/vagrant/definition.def .
```

# 4. Build a docker container and convert it to singularity
Example: I built FSL based on https://github.com/BIDS-Apps/dockerfile-templates/blob/master/FSL/Dockerfile
go to the local directory where dockerfile exists
```
docker build -t fslnine .
docker tag f6b20d2fbb99 jungheejung/fslnine:latest
docker push jungheejung/fslnine:latest
```
If your HPC doesn't allow for docker, but has singularity,
here's how to convert dockers into singularity containers.
```
docker run --privileged -t --rm \
-v /var/run/docker.sock:/var/run/docker.sock \
-v /Users/h/Documents/singularity-vm:/output \
singularityware/docker2singularity \
jungheejung/fslnine:latest
```
