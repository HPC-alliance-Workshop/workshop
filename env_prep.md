---
title: Environment preparation
layout: default
nav_order: 3
---

# Prepare the Environment
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}


## Retrieve the tutorial code

```shell
git clone https://github.com/Compute-Canada-Workshop/UCMerced_classification.git
cd UCMerced_classification
```



## Load necessary modules

```shell
module load python/3.8
module load cuda/11.0
module load scipy-stack
```

## Create and activate a virtual environement

```shell
virtualenv --no-download $SLURM_TMPDIR/ucmerced
source $SLURM_TMPDIR/ucmerced/bin/activate
```

## Installing packages

```shell
pip install --no-index --upgrade pip
pip install torch torchvision --no-index
pip install scikit-image --no-index
pip install tqdm --no-index

```



