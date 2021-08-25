# OpenABC-D: A Large-Scale Dataset For Machine Learning Guided Integrated Circuit Synthesis 
[![Version](https://img.shields.io/badge/Version-1.0.0-brightgreen)](https://github.com/NYU-MLDA/OpenABC) 
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)

## Overview

**OpenABC-D** is a large-scale labeled dataset generated by synthesizing open source hardware IPs using state-of-art open source logic synthesis tool **yosys-abc**. We consider 29 open-source hardware IP designs collected from various sources like IWLS, OpenROAD, OpenPiton etc, and performed combinational logic synthesis with 1500 random synthesis flows (we hereby call them *synthesis recipes*) using **yosys-abc**. Each synthesis flow is of a predefined length **L** (L=20, in our case). We preserved all AIGs: starting, intermediate and final AIGs with labels like number of nodes, longest path, sequence of atomic synthesis transofrmations applied along graph statistics and area and delay of final AIG. 

We converted the AIGs in **pytorch** data format that can be directly used by a machine learning engineer lessening the effort of costly labeled data generation and pre-processing. **OpenABC-D** can be used for a variety of learning tasks on logic synthesis like 1) Predicting quality of result (QoR) performance of a synthesis recipe 2) area and delay prediction post techonolgy mapping, 3) Learn functional and structural features using self-supervision to encode rich AIG state information for reinforecement learning guided logic synthesis etc. Our dataset can easily be used for graph-based machine learning framework like [Pytorch-Geometric](https://github.com/rusty1s/pytorch_geometric). The data generation pipeline of **OpenABC-D** is shown as follows:
![](https://github.com/NYU-MLDA/OpenABC/blob/master/figures/DatagenerationPipeline.png)


## Installing dependencies

We recommend using [venv](https://docs.python.org/3/library/venv.html) or [Anaconda](https://www.anaconda.com/) environment to install pre-requisites packages for running our framework and models.
We list down the packages which we used on our side for experimentations. We recommend installing the packages using *requirements.txt* file provided in our repository.

- cudatoolkit = 10.1
- numpy >= 1.20.1
- pandas >= 1.2.2
- pickleshare >= 0.7.5
- python >=3.9
- pytorch = 1.8.1
- scikit-learn = 0.24.1
- torch-geometric=1.7.0
- tqdm >= 4.56
- seaborn >= 0.11.1
- networkx >= 2.5
- joblib >= 1.1.0

Here are few resources to install the packages (if not using *requirements.txt*)

- [Pytorch](https://pytorch.org/get-started/locally/)
- [Torch-geometric](https://pytorch-geometric.readthedocs.io/en/latest/notes/installation.html)
- [Networkx] (https://networkx.org/documentation/stable/install.html)

Make sure that that the cudatoolkit version in the gpu matches with the pytorch-geometric's (and dependencies) CUDA version.

## Organisation






