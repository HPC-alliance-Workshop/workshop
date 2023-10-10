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
git clone https://github.com/HPC-alliance-Workshop/UCMerced_classification.git
cd UCMerced_classification
```

## Request and check resources 

```shell
salloc --time=01:00:00 --mem=10G --gpus=1 --account=def-sponsor00
```
```shell
nvidia-smi
```

## Load necessary modules

```shell
module load python/3.10
```

## Create and activate a virtual environement

```shell
virtualenv --no-download $SLURM_TMPDIR/venv
source $SLURM_TMPDIR/venv/bin/activate
```

## Installing packages

```shell
pip install --no-index -r requirements.txt

```



