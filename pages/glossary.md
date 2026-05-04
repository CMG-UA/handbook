---
title: Glossary
nav_order: 1
parent: FAQ's   # optional grouping
---
# Glossary

A beginner-friendly list of common terms you may see when working with code, GitHub, and servers.

---

## A

### API (Application Programming Interface)
A defined way for one tool to talk to another.  
Example: a script can use a GitHub API to list files in a repository automatically.

### Apptainer (formerly Singularity)
A container system often used on HPC (high‑performance computing) clusters.  
Like Docker, it packages software and its dependencies, but it’s designed to work well on shared servers.

---

## B

### Branch
A separate “version line” of the code in Git.  
You can make changes in a branch without affecting the main code until you merge it.

### Build
The process of turning source code (and configuration) into something runnable, like an installed package or a container image.

---

## C

### CLI (Command Line Interface)
A way to interact with a computer by typing commands in a terminal instead of clicking buttons.

### Cluster
A group of servers working together (common in research computing).

### Commit
A saved checkpoint of changes in Git.  
A commit includes *what changed* and usually a short message describing why.

### Conda
A package and environment manager commonly used for Python (and other languages).  
It helps you install dependencies and keep project environments separated.

### Container
A packaged, isolated runtime environment that includes an application and everything it needs to run.  
Containers help ensure “it runs the same everywhere”.

---

## D

### Dependency
A library/tool your code needs in order to run (for example: NumPy for Python).

### Directory (Folder)
A container for files and other directories.  
On most systems, “directory” and “folder” mean the same thing.

### Docker
A popular container platform.  
Docker images can package software so it runs the same on different machines, but some shared servers/HPC systems prefer Apptainer instead.

---

## E

### Environment (software environment)
A set of installed packages and settings used for a project.  
Example: one environment for Project A and a different one for Project B, so they don’t conflict.

---

## F

### File path
The “address” of a file on a computer.  
Example: `data/raw/samples.csv` (a file inside the `data` directory, then `raw`).

### Fork
Your own copy of someone else’s GitHub repository under your account.  
You can experiment safely and propose changes back via a pull request.

---

## G

### Git
A tool for tracking changes in files over time (version control).  
Git helps you collaborate, revert mistakes, and understand project history.

### GitHub
A website that hosts Git repositories and adds collaboration features (issues, pull requests, reviews).  
Think of it as “Google Docs for code” (with extra tools).

### Git repository (repo)
A project folder tracked by Git, including the full history of changes.

---

## H

### HPC (High‑Performance Computing)
Powerful shared computing resources used for large or long-running jobs (common in universities/research).

---

## I

### Issue
A GitHub item used to track work: bugs, questions, tasks, or feature requests.  
Issues are great for documenting decisions and progress.

---

## J

### Job
A unit of work you run on a server or HPC system (often submitted to a scheduler).  
Example: “run this analysis script for 4 hours using 8 CPUs”.

### Job scheduler
Software that manages *who gets to use which compute resources and when* on a shared cluster.  
Instead of everyone running heavy programs directly on login nodes, you submit jobs and the scheduler starts them when resources are available.

---

## L

### Linux
An operating system widely used on servers and HPC systems.  
Many “server commands” are Linux commands.

### Local machine
Your own laptop/desktop computer (as opposed to a remote server).

### Login node
A server you connect to first on an HPC system (often via SSH).  
You typically use it to prepare files and submit jobs, not to run heavy computations.

---

## M

### Main branch
The default primary branch of a repository (often called `main` or sometimes `master`).  
It usually represents the most stable version of the project.

### Merge
Combining changes from one branch into another (often into `main`).

---

## O

### Open source
Software whose source code is publicly available and can usually be used/modified under a license.

---

## P

### Partition (Slurm)
A named group of compute nodes in a Slurm cluster.  
Partitions often represent different hardware or policies (e.g., `cpu`, `gpu`, `long`). You request a partition when submitting a job.

### Pull request (PR)
A GitHub request to merge changes from one branch into another.  
It’s a common way to propose changes, get review, and keep a record of discussion.

---

## Q

### Queue
A waiting line for jobs on a cluster.  
Your job may wait in the queue until the requested resources are free.

---

## R

### README
A (usually) `README.md` file that explains what a repository is, how to install it, and how to use it.

### Remote
A copy of your Git repository stored somewhere else (commonly on GitHub).  
Your computer has a local copy; GitHub hosts a remote copy.

### Repository hosting
A service (like GitHub) that stores Git repositories online.

---

## S

### sbatch (Slurm)
A Slurm command used to submit a batch job script to the scheduler.  
You write a script describing resources needed (time, CPUs, memory) and what commands to run, then submit it with `sbatch`.

### salloc (Slurm)
A Slurm command used to request an interactive allocation of resources.  
Useful when you want a “live” session to run commands interactively on compute resources.

### srun (Slurm)
A Slurm command used to run a program as part of a job/allocation.  
Often used inside an `sbatch` script or after `salloc`.

### scancel (Slurm)
A Slurm command used to cancel a queued or running job.

### squeue (Slurm)
A Slurm command that shows jobs currently in the queue (waiting or running).

### Slurm
A widely used job scheduler for HPC clusters.  
It controls access to shared compute resources: you request resources (CPUs/GPUs/memory/time), submit a job, and Slurm runs it when resources are available.

### Server
A computer that provides services to other computers (often accessed remotely).  
In practice: “a computer you connect to over the network to run code or store data”.

### Shell
The program that reads your terminal commands (e.g., `bash`, `zsh`).  
It’s the “command interpreter”.

### SSH (Secure Shell)
A secure way to connect to another computer (like a server) through the terminal.  
Example: you can use SSH to log into a remote machine without physically being there.

---

## T

### Terminal
A text-based window where you type commands (especially common on Linux/macOS and servers).

### Time limit / wall time (Slurm)
The maximum amount of real clock time your
