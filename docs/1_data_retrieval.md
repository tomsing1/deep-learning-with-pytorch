# Retrieving LUNA16 data from Zenodo

The data from LUNA16 challenge is available from Zenodo.
Because it is larger than the maximum size for a single
Zenodo repository (50Gb), there are two separate repos:

- [LUNA16 Part 1/2](https://zenodo.org/record/3723295)
  - `annotations.csv`
  - `candidates.csv`
  - Data subsets 0-6
  
- [LUNA16 Part 2/2](https://zenodo.org/record/4121926)
  - Data subsets 7-9

## Downloading files from Zenodo

I downloaded the files listed above onto the luna16 folder on my 
paperspace instance with the follwing interactive `wget`
commands:

```bash
wget https://zenodo.org/record/3723295/files/annotations.csv
wget https://zenodo.org/record/3723295/files/candidates.csv

# data files from the first repository
for N in {0..6}
do 
  wget "https://zenodo.org/record/3723295/files/subset${N}.zip"
done

# data files from the second repository
for N in {7..9}
do
  wget "https://zenodo.org/record/4121926/files/subset${N}.zip"
done

```

## Decompressing the image files

The image files are in compressed archives that must be decompressed
with [7z](https://packages.debian.org/sid/p7zip-full).

```bash
sudo apt update
sudo apt install p7zip-full
for N in {0..9}
do 
  7z x "subset${N}.zip"
done
```

## Data files

Each CT scan is provided in 2 files:

1. `.mhd` metadata text file
2. `.raw` MetaIO file

with the same UID filename.

For example, metadata looks like this:

```
ObjectType = Image
NDims = 3
BinaryData = True
BinaryDataByteOrderMSB = False
CompressedData = False
TransformMatrix = 1 0 0 0 1 0 0 0 1
Offset = -198.10000600000001 -195 -335.209991
CenterOfRotation = 0 0 0
AnatomicalOrientation = RAI
ElementSpacing = 0.7617189884185791 0.7617189884185791 2.5
DimSize = 512 512 121
ElementType = MET_SHORT
ElementDataFile = 1.3.6.1.4.1.14519.5.2.1.6279.6001.105756658031515062000744821260.raw
```
