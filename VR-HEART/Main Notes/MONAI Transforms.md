2024-06-15 18:22

Tags : [[transforms]] #transforms 

# Transforms in MONAI

The transforms in MONAI are of tow types:

- Array transforms
- Dictionary transforms

Array transforms are meant to be used on single images or a folder of images. Dictionary transforms on the other hand are used on more complicated data structures. They take in a dictionary and perform the transforms.

The same kind of transform brings about the same change in the image, regardless of what kind of transform it is. The only difference being that the data structure being affected is different.  

## Different kinds of MONAI transforms

### [[LoadImage]]

The LoadImage transform essentially takes in a path in the case for the Array transform or a dictionary type object in the case for the dictionary transform, and converts it into either a PyTorch tensor object or a numpy array object.  

### [[EnsureType]]
Ensures the the image is loaded in the correct format, ie either Numpy array or PyTorch tensor.

### [[ScaleIntensity]]

Scales the values of the pixels to be in the range of 0 to 1. This parameter can be changed using parameters.

### [[Spacingd]]

### [[Orientationd]]

# References 
