
Moved
https://www.notion.so/CPU-Disk-Bottleneck-e3f3d65c87684a7a8eb5223fa64e3c27

# Links

[[cs231n]]

[[DataLoader]]
[[Memory]]

# Formats

[[HDF5]]

LMBD
Lightning Memory-Mapped Database
https://en.wikipedia.org/wiki/Lightning_Memory-Mapped_Database

hdf5 vs. lmdb

cifar10 dataset format?

# Overview


Big folder full of JPEG images is bad.
- each image can be located in different parts of the disk - random seek
- once you read the JPEG you need to decompress it into pixels

Preprocess to one giant continuous file with raw pixels and save to disk

Most efficient way to use a large data set for PyTorch?
https://stackoverflow.com/questions/53576113/most-efficient-way-to-use-a-large-data-set-for-pytorch