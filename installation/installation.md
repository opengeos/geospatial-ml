# Installation

The **geospatial-ml** package has many dependencies, such as [GeoPandas](https://geopandas.org) and [localtileserver](https://github.com/banesullivan/localtileserver). These optional dependencies can sometimes be a challenge to install, especially on Windows. Therefore, we advise you to closely follow the recommendations below to avoid installation problems.

<!-- ## Video Tutorial

[![Introducing geospatial](images/thumbnail.png)](https://youtu.be/Y1xB7d2VbFY "Introducing geospatial") -->

## Installing with Anaconda/Miniconda

To install geospatial-ml and all its dependencies, we recommend you use the [conda](https://conda.io/en/latest) package manager. This can be obtained by installing the [Anaconda Distribution](https://www.anaconda.com/distribution) (a free Python distribution for data science), or through [Miniconda](https://docs.conda.io/en/latest/miniconda.html) (minimal distribution only containing Python and the conda package manager). See also the [installation docs](https://conda.io/docs/user-guide/install/download.html) for more information on how to install Anaconda or Miniconda locally.

### Using the conda-forge channel

Geospatial-ml is available on the [conda-forge](https://anaconda.org/conda-forge/geospatial-ml) channel, a community effort that provides [conda packages](https://conda-forge.org) for a wide range of software.

```bash
conda install -c conda-forge geospatial-ml
```

### Creating a new conda environment

Creating a new environment is not strictly necessary, but given that some geospatial-ml dependencies might have a version conflict with other geospatial-ml packages in an existing conda environment, it is a good practice to install geospatial-ml and its dependencies in a clean environment starting fresh.

The following commands create a new conda environment with the name `geo` and install geospatial-ml and its dependencies (e.g., GeoPandas, localtileserver) in it:

```bash
conda create -n geo python=3.9
conda activate geo
conda install geopandas
conda install geospatial-ml -c conda-forge
```

**Important note:** If you are using Windows, we advise you to closely follow the installation instructions above to install GeoPandas from the default conda channel (`conda install geopandas`) rather than from the conda-forge channel. This can avoid a potential `spatialindex_c-64.dll` error when using GeoPandas ([source](https://github.com/geopandas/geopandas/issues/1812)). If you are using Linux or macOS, it is okay to install all geospatial-ml dependencies from the conda-forge channel with the following command:

```bash
conda install -c conda-forge geospatial-ml
```

### Using Mamba

When installing packages using the conda package manager, sometimes it can take a while for conda to resolve dependencies. If it takes too long or fails to resolve dependencies, you can try using the [Mamba](https://mamba.readthedocs.io/en/latest) package manager to install geospatial-ml and its dependencies. Mamba is a fast, robust, and cross-platform package manager. It runs on Windows, macOS, and Linux, and is fully compatible with conda packages and supports most of conda’s commands. Once Mamba is installed in a conda environment, you can then simply replace any `conda` command with `mamba`. For example, to install geospatial-ml and its dependencies with Mamba, you can use the following commands:

```bash
conda create -n geo python=3.9
conda activate geo
conda install -c conda-forge mamba
mamba install geopandas
mamba install -c conda-forge geospatial-ml
```

## Installing with pip

geospatial-ml is also available on [PyPI](https://pypi.org/project/geospatial-ml). It can be installed with pip using the following command:

```bash
pip install geospatial-ml
```

All optional dependencies of geospatial-ml are listed in [requirements_dev.txt](https://github.com/giswqs/geospatial-ml/blob/master/requirements_dev.txt).

## Installing from source

You may install the latest development version by cloning the GitHub repository with [Git](https://git-scm.com) and using pip to install from the local directory:

```bash
git clone https://github.com/giswqs/geospatial-ml.git
cd geospatial-ml
pip install .
```

It is also possible to install the latest development version directly from the GitHub repository with:

```bash
pip install git+https://github.com/giswqs/geospatial-ml.git
```

## Upgrading geospatial-ml

If you have installed geospatial-ml before and want to upgrade to the latest version, you can run the following command in your terminal:

```bash
pip install -U geospatial-ml
```

If you use conda, you can update geospatial-ml to the latest version by running the following command in your terminal:

```bash
conda update -c conda-forge geospatial-ml
```
