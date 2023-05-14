## Setting up a cloud workstation    

The datasets used in part 1 of the book are usually small, 
and the code often uses data sources that can be loaded with
built-in PyTorch functions. This allowed me to work through
the chapters using Google Colab.

To step throught the examples of part 2 of the book, I created a 
Notebook project on [Paperspace gradient](https://www.paperspace.com/)
to 

1. get access to more powerful GPUs and
2. leverage storage on AWS S3 (and mount buckets as if they were posix folders)
 
### Installing dependencies

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

### Data storage on AWS S3

Because the free storage capacity of a Paperspace Gradient notebook is limited,
I stored the decompressed LUNA16 data in an AWS S3 bucket instead. The bucket
[is mounted as a dataset](https://docs.paperspace.com/gradient/data/#configure-your-storage-bucket) 
in the `/datasets/luna16` folder of the virtual server (but the files are
actually read from S3).

