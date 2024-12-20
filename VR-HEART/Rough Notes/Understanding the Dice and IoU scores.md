
2024-06-28 
18:39

Tags : #ai-general #metrics


# Understanding the Dice and IoU scores

## Why?

A very interesting application of AI models is in the field of semantic segmentation. The output of this process being a simple "mask", that indicates where all the members of a particular class exist. 

The way any AI model learns is by understanding the errors or mistakes that it made in a run, then adjusting itself based on said error and then taking a swing at the problem again. This process of  learning is done until we finally get good results and we are satisfied with the performance of the model in the task that was specified.

Ok that sounds cool, but how do you calculate this "error"?  That is where the [[Dice Score]] and [[IOU Score]]  come to help us. 

## How do they help us?

How would you differentiate two images? By the way that each looks and how one looks different from the other. Thinking about it a bit more deeply, we are comparing the pixels from each other. So the similarity or disimilarity between two images can be considered in terms of the the number of similar pixels or dissimilar pixels.
Ok now, that we have that fact, let us consider  what we are working with right now.

We have 2 images, the one generated by the model (we call that the predicted mask), and the other being the one that we give, (what we call the ground truth). Now we have to compare these two and find out how much error the model made when generating the mask. In our specific case, the pixels in these images can have two values, 0 and 1. They are binary in nature. 

[insert examples here]

Now to start measuring the error, we need to basic binary operations, the logical OR and the logical AND. The logical OR returns a positive in when atleast one of the values is positive, and only returns negative when both values are also negative. The logical AND operation returns a positive value if and only if both the values are positive, in all other cases, it returns negative.

Note: Postive -> 1, Negative -> 0

Now lets think about this in terms of images, when we do a pixel-wise AND operation on the two images, we will get a new mask that contains a positive value in the pixel positions where there was a positive in both the predicted and  ground truth images. Similarly doing a pixel-wise OR operation would lead to a mask which would have postive values wherever there was a positive in either of the images.

The **AND** operation corresponds to the operation called **Intersection** and the **OR** operation corresponds to the operation called **Union**.

The intersection is essentially the number of True positives and the union is a collection of the True positives,  False positives and False negatives. 

Thus the expression for Dice Score can be given as:
![[Pasted image 20240701111129.png]]


and the iou can be given as:
![[Pasted image 20240701111154.png]]





# References 
