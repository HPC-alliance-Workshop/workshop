---
title: Running the tutorial
layout: default
nav_order: 4
---

# Prepare the Environment
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}


## Run the training code

```shell
python train.py --dataset_path $SLURM_TMPDIR/UCMerced_LandUse
```

The model is stored in the folder `weights`. You can also see the loss and accuracy graphs saved in the working directory. 


## Run Inference

```shell
python predict.py --dataset_path $SLURM_TMPDIR/UCMerced_LandUse --weight_path weights/model_epoch18.pth
```

The predictions are saved into `predictions.png`. 


