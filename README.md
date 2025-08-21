# Purdue AF Conda environments / Jupyter kernels

This repository contains recipes used to build Conda environments and Jupyter kernels at Purdue Analysis Facility.

There is a job that runs every few hours and builds a Conda environment from each of these recipes at `/work/kernels/` and at `/depot/cms/kernels`.

To add your own environment, please open a pull request.


## Repository structure

Each top-level directory corresponds to a conda environment with the same name.
Inside each directory, there should be an `environment.yml` or `environment.yaml` file
with a list of Conda (and Pip, if needed) packages to be installed.

[How to create environment.yaml](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-file-manually)

Additionally, a directory can contain `pip-uninstall.txt` with a list of packages you want uninstalled after `environment.yaml` is built. This can be useful if some package installed via `pip` comes with an unwanted dependency.


## Curated environments

Two main environments are maintained by Purdue AF admins. These environments are also by default available in Jupyter notebooks as kernels.

### 1. `python3` Environment
- **Purpose**: Default, stable environment meant to serve most Purdue AF use cases. Start with this environment and feel free to open a pull request to add any missing packages.
- **Key Features**:
  - Python 3.10.10
  - TensorFlow 2.15.1 with CUDA support
  - PyTorch 2.0.1 with geometric extensions
  - Coffea 0.7.21
  - Extensive plotting and visualization tools

### 2. `coffea_latest` Environment
- **Purpose**: Stay in tune with latest developments in the HEP software stack, primarily [Coffea](https://coffea-hep.readthedocs.io/en/latest/)
- **Key Features**:
  - Regularly updated Coffea releases
  - Dependencies such as Dask, Uproot, Awkward are generally more recent than in `python3` environment


## Adding your own environment

If your analysis has requirements not covered by existing environments, please open a pull request to this repository. You can either suggest an update to existing environments, or create your own top-level directory, taking `python3` or `coffea_latest` as an example.




