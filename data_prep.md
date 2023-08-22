---
title: Data Preparation and transfer
layout: default
nav_order: 4
---

# Download and transfer the data
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## 1. UC Merced Land Use Dataset

This is a 21 class land use satellite image dataset [^1] with 100 images for each of the following classes :


| agricultural| beach | buildings |
|harbor|baseballdiamond|airplane|
|intersection |forest |  mobilehomepark | 
| chaparral  |denseresidential|freeway| 
| golfcourse  |overpass| parkinglot | 
|river |runway|sparseresidential|
storagetanks|tenniscourt|mediumresidential|

Each image measures 256x256 pixels.

![Alt Text](assets/img/ucm.png)


## 2. Download the dataset

You can download the dataset zip file [here](http://weegee.vision.ucmerced.edu/datasets/landuse.html). 


## 3. Transfer the dataset 
### Windows


### Linux

```shell
scp '/path/to/UCMerced_LandUse.zip' 'username@cedar.computecanada.ca:./scratch'
```

## 4. Unzip the dataset 


```shell
unzip ~/scratch/UCMerced_LandUse.zip -d ~/scratch
```

The dataset is now inside `~/scratch/UCMerced_LandUse`

[^1]: Yi Yang and Shawn Newsam, "Bag-Of-Visual-Words and Spatial Extensions for Land-Use Classification," ACM SIGSPATIAL International Conference on Advances in Geographic Information Systems (ACM GIS), 2010.
