# Reproducible Research 2

The authors divide RR into three areas of interest:
* Managing data
* Managing software
* Managing computations


# Managing data

# Managing software

Code availability is not enough for reproducibility,
it is also necessary to provide an reproducible environment with all the code dependencies.

1. Identify all software dependencies
2. Choose a tool that enables creating this environment
3. Write a manifesto

## Guix ❤️

## Docker/Singularity

# Managing computations

Konrad splits the software stack into 6 layers (top down):
1. Project automation
2. Domain-specific software
3. Scientic infrastructure (HDF5, MPI, BLAS, OpenMP,...)
4. Non-scientific infrastructure (Python, gcc,...)
5. Operating system (GNU/Linux)
6. Hardware
   
Layer 2 is `Domain-specific software` with simulation software and data analysis tools.

>[!NOTE]
>"One way to look at the software in each layer is as a recipe in automating steps that are executed in the layers below"

Software at the **bottom layers** rarely change, so they benefit from **optimization**.
Software at the **top layers** change all the time at the cost of the research project, so they benefit from malleability.


Layer 1 perform the automation of all steps required for a specific research project.
There are mainly 3 types of automations at layer 1:

**Scripts:**
* Simple and easy: one command to run
* But: runs everything every time!

**Notebooks:**
* Run individual cells...
* By hand, order dependent - not reproducible! 

**Workflows:**
* Subdivide computation into *tasks*
* Each task reads input from files and write to them
* Allows to Re-run a task only when code or input data have changed
* Reproducible

## Resource management

Parallel computing
* Run independent tasks in parallel
* Run parallelized tasks on multiple CPUs

Storage of intermediate/final results
* local fs

Software environments

## Workflow managers

The function of a workflow managers can be described as follows:
* Reads a workflows descriptions
* Run tasks, avoiding duplication
* Manage storage of intermediate results\
* Manage resources
