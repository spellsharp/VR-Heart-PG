2024-06-22 
13:44

Tags : #ai-general #metrics [[metrics]] [[ai-general]]

# What is the Dice Score?

The dice score is a error calculation metric which is used for image segmentation. This is very similar to the [[IOU Score]] metric, but they have some slight differences.

The formula for calculating dice score of a segmentation is as follows:

			![[Pasted image 20240622135040.png]]


So the equation comes out to:

2 times the intersection of the mask and ground truth. divided by the sum of area/ number of pixes in the mask and the number of pixels in the ground truth.

# References 

[DICE (or Dice) Score](https://medium.com/@saba99/dice-or-dice-score-fa9f70422db4)
