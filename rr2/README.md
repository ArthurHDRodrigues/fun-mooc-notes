# Reproducible Research 2

The authors divide RR into three areas of interest:
* Managing data
* Managing software
* Managing computations


## Managing data

## Managing software

Code availability is not enough for reproducibility,
it is also necessary to provide an reproducible environment with all the code dependencies.

1. Identify all software dependencies
2. Choose a tool that enables creating this environment
3. Write a manifesto

### Guix ❤️

### Docker/Singularity

## Managing computations

Konrad splits the software stack into 6 layers (top down):
1. Project automation
2. Domain-specific software
3. Scientic infrastructure (HDF5, MPI, BLAS, OpenMP,...)
4. Non-scientific infrastructure (Python, gcc,...)
5. Operating system (GNU/Linux)
6. Hardware

Layer 1 perform the automation of all steps required for a specific research project.

Layer 2 is `Domain-specific software` with simulation software and data analysis tools.

>[!NOTE]
>"One way to look at the software in each layer is as a recipe in automating steps that are executed in the layers below"

Software at the **bottom layers** rarely change, so they benefit from **optimization**.
Software at the **top layers** change all the time at the cost of the research project, so they benefit from malleability.
