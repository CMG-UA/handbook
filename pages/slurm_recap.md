---
title: SLURM recap
nav_order: 4
parent: Handbook   # optional grouping
---
# SLURM recap
Here you can find a small and helpful info for slurm usage. 

## Running a script with sbatch

Create a SLURM submission script like this:
```
#!/bin/sh
#SBATCH --job-name=test               # Job name
#SBATCH --nodes=1                    # Number of nodes
#SBATCH --cpus-per-task=1            # CPUs per task
#SBATCH --mem=1GB                    # Memory per node
#SBATCH --time=01:00:00              # Time limit (HH:MM:SS)
#SBATCH --output=my_job.%j.out       # Standard output
#SBATCH --error=my_job.%j.err        # Standard error
#SBATCH --chdir=/home/mhannaert/     # Working directory
#SBATCH --partition=batch            # Partition or queue

echo "Hallo Marie"
I=0
while [ "$I" -lt 10 ]; do
    echo "$I" >> test_slurm.txt
    I=$((I+1))
done
sleep 30
```
Submit it with:
```
sbatch <your_sbatch_script>.sh
```
## Running an interactive session with srun
````
srun --job-name=<your_job_name> --time=02:00:00 --pty bash -i
````
## Using SLURM with Workflow Managers

Nextflow:
[Nextflow docs](https://www.nextflow.io/docs/latest/executor.html)

Set process.executor = 'slurm' in your nextflow.config. SLURM options like cpus, memory, and time can be controlled with process directives.

Snakemake:
[Snakemake docs](https://snakemake.readthedocs.io/en/stable/executing/cli.html#profiles)

Use a SLURM profile or specify the --profile option when running Snakemake.

## Useful commands to followup your jobs 

Seeing the job in the queue
````
squeue
````
Getting info about the nodes
````
sinfo
````
Canceling a job (first with ID, second all the jobs of a yourself)
````
scancel <ID out of squeue>
scancel -u <your username>
````

>If you’re unsure about how to set this up or if you have any doubts, please come talk to me before launching anything, I’m happy to help!