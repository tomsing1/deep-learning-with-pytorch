# Deep Learning with PyTorch

[This repository](https://github.com/tomsing1/deep-learning-with-pytorch)
documents my progress of working through the 
[Deep Learning with PyTorch](https://github.com/deep-learning-with-pytorch/dlwpt-code)
book and the associated code examples.

The book contains three parts:

- Part 1: an introduction into deep learning modules and PyTorch.
- Part 2: developing ML models to analyze Ct scans for cancer detection.
- Part 3: Deployment

## Table of contents

### Docs

I have documented my learning steps, e.g. setting up a cloud workstation, or
the download & storage of the LUNA16 dataset, in the `docs` folder:

- [Setting up a cloud workstation](docs/0_setting_up_a_cloud_workstation.md)
- [Data retrieval and storage](docs/1_data_retrieval.md)

### Notebooks

My Jupyter notebooks are in the `notebooks` subfolder.

## Prerequisites

The code in was executed in the `PyTorch 1.12` docker image on paperspace.
Additional dependencies that need to be installed are documented in the 
`requirements.txt` file. (Additional modules don't persists on paperspace
between restarts of the notebook environment.)

## Helper modules

Part 2 of the book includes a number of helper modules provided by the
authors, e.g.

- `p2ch10/`
  - `dsets.py`
  - `vis.py`
- `util/`
  - `disk.py`: defines the `GzipDisk` class and provides the `getCache()` function to set up a `diskcache.FanoutCache`.
  - `logconf.py`
  - `unet.py`
  - `util.py`

## Useful references

- [PEP 8 – Style Guide for Python Code](https://peps.python.org/pep-0008/)
- [Jupyterlab - common keyboard shortcuts](https://gist.github.com/discdiver/9e00618756d120a8c9fa344ac1c375ac)
- [IPython cell magics](https://nbviewer.org/github/ipython/ipython/blob/1.x/examples/notebooks/Cell%20Magics.ipynb)
- [Installing Python Packages from a Jupyter Notebook](https://jakevdp.github.io/blog/2017/12/05/installing-python-packages-from-jupyter/)