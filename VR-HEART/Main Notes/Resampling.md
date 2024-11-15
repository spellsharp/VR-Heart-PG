2024-06-20 
21:31

Tags : #transforms 

# What is resampling?

Resampling in MONAI is a technique in which the spatial characteristics of the image are changed. This mainly done by the use [[MONAI Transforms]]. This involved interpolating the image into another grid.

## Why use resampling?

Resampling is mainly done for the purposes of preprocessing, ie; standardizing the spatial characteristic of the images throughout the pipline.

Some common examples of resampling transforms are: 
- [[Spacingd]]
- [[Orientationd]]

## What are some issues with resampling?

Traditionally, the transforms ie; the resampling is done sequentially, as we are makign changes to the spatial dimensions of the image, this may result in some parts of the image being lost. This is a very big issues when it comes to medical AI as there is a chance that some important feature or region may also be removed due to this.

Transforms like the RandSpatialCropd or RandZoomd, mess around with the spatial features of the image, this would result in the 

# References 

