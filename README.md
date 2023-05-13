# Deep Learning with PyTorch

This repository documents my progress of working through the 
[Deep Learning with PyTorch](https://github.com/deep-learning-with-pytorch/dlwpt-code)
book and the associated code examples.

The book contains three parts:

- Part 1: an introduction into deep learning modules and PyTorch.
  - Datasets are usually small, and the code often uses data sources that
    can be loaded with built-in PyTorch functions. This allowed me to
    work through the chapters using Google Colab.
- Part 2: developing ML models to analyze Ct scans for cancer detection.
  - The full [LUNA16](https://zenodo.org/record/3723295)
    dataset is relatively large (~ 225 Gb of uncompressed images), exceeding
    the storage available in Google Colab. 
- Part 3: Deployment

## Setting up a cloud workstation    

To step throught the examples of part 2 of the book, I created a Notebook project
on [Paperspace gradient](https://www.paperspace.com/).
 
## Installing dependencies

The [book's github repository](https://github.com/deep-learning-with-pytorch/dlwpt-code)
includes a `requirements.txt` file, specifying version numbers (or ranges) for
various python modules. I installed these requirements in the Paperspace
notebook (without using a virtual environment, because Paperspace provides a
separate, containerized environment for each project):

```bash
pip install pip install -r requirements.txt
```

Due to changes in availability, I had to relax the versions for `numpy` and
`tensorflow`. The final environment is documented in the `requirements.txt`
file in this repository.

I have documented additional steps, e.g. the download & storage of the
LUNA16 dataset, in the `docs` folder:

1. [Data retrieval and storage](docs/0_data_retrieval.md)


    
