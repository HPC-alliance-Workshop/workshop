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
cp -r ../UCMerced_classification/ .
cd UCMerced_classification
```

## Request and check computing resources 

```shell
salloc --time=01:00:00 --mem=10G --gpus=1 --account=def-sponsor00
```
We have requested 10G of memory (RAM) and 1 GPU for the job for 1 hour. 

```shell
nvidia-smi
```
This command is used to display information about GPU devices on a system.

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



