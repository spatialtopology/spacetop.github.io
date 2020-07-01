---
layout: default
title: Equipment setup
parent: Running experiments
permalink: /runningexp/ST
nav_order: 2
---

# Equipment setup
{: .no_toc }
{: .fs-11 }


## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

# DBIC PC setup + DBIC daily setup

---


# TSA-II

---

# Singularity container

---

# Installing PTB on linux
check installation
* neurodebian
* neurodocker
* anaconda
* singularity


worked for Luke
 http://neuro.debian.net/install_pkg.html?p=psychtoolbox-3-common

 Yarik suggestion
 You need to add contrib (probably no need for non-free) portion in addition to main in your NeuroDebian apt file.
* https://wiki.debian.org/SourcesList
* `cat /etc/apt/sources.list.d/neurodebian.sources.list`


Getting error message:
> libGL error: MESA_LOADER: failed to open readeonsi (search paths /usr/lib/x86_64-linux-gnu/dri:\$${ORIGIN}/dri:/usr/lib/dri)
libGL error: failed to load driver: readeonsi
failed to create dri screen

-> https://psychtoolbox.discourse.group/t/matlab-crashes-after-insatlling-ptb-com-jogamp-opengl-glexception/74
