2024-06-15  17:54

Tags :  [[transforms]] #transforms

# The basics of transforms and why they are needed in the ecosystem

Transforms are generally used to introduce some sort of change in the input image.  The main point of doing this is do something called [[Data Augmentation]]. 

MONAI has a lot of these transforms each serving different purposes. 

The ``Transform`` base class can even be used to make  custom transforms for specific use cases. 
\
The ``MapTransform`` class can be used to extend the functionality of the parent Transform base class to be able to apply transforms on mutable objects like a ``dict``.

For more info about Transforms in MONAI, this is the link [[MONAI Transforms]]
# References 

[MONAI Transforms documentation](https://docs.monai.io/en/stable/transforms.html)

[MONAI Bootcamp 2021](https://www.youtube.com/watch?v=Ih-4xzRJYO0&list=PLtoSVSQ2XzyCobzE6NvwjNpITsQyPUtfs&index=2)
