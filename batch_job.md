---
title: Submitting a Batch Job 
layout: default
nav_order: 5
---

# Prepare the Environment
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

This guide will walk you through writing and understanding a Slurm batch job script for submitting a training job.

# A batch job script
Below is an example of a basic batch job script, explained step-by-step.

**Filename:** `job_script.sh`
```shell
#!/bin/bash
#SBATCH --time=00:15:00              # Job time limit (HH:MM:SS)
#SBATCH --account=def-sponsor      # Account to charge
#SBATCH --mem=32000M                    # Memory allocation
#SBATCH --gres=gpu:1            # Number of GPUs per node
module load python/3.6
# Prepare virtualenv
source ~/my_env/bin/activate
# Prepare data
mkdir $SLURM_TMPDIR/data
tar xf ~/projects/def-xxxx/data.tar -C $SLURM_TMPDIR/data
# Start training
python train.py $SLURM_TMPDIR/data
```

## Header and Basic Resource Requests
1. **`#!/bin/bash`**: Specifies the script interpreter (Bash in this case). 
2. **`#SBATCH --time=00:15:00`**: Allocates 15 minutes for the job. Adjust as needed.
3. **`#SBATCH --account=def-sponsor00`**: Indicates the account to be billed for the resources.
4. **`#SBATCH --mem=3200M`**: Requests 3G of memory for the job. Adjust according to your program's needs.
5. **`#SBATCH --gres=gpu:1`**: Requests 1 GPU for the job. Replace `1` with the required number of GPUs if needed.

for additional SBATCH options, please see [https://docs.alliancecan.ca/wiki/Running_jobs](https://docs.alliancecan.ca/wiki/Running_jobs)

## Exercice : Writing a Batch script

Previously, you used **`salloc`** to create an interactive job and executed a series of commands directly in the terminal. Now, your task is to write those commands into a batch script file named job_script.sh.

- Include the necessary SBATCH directives for resource allocation (time, memory, GPUs, etc.).
- Transfer the script from your local computer using scp 
```shell
scp '/path/to/job_script.sh' 'user@laval-crdig.calculquebec.cloud:./projects/def-sponsor00/user{id}/'
```


# Submitting the Job

```shell
sbatch job_script.sh
```
# Monitoring the Job
```shell
squeue -u $USER
```
