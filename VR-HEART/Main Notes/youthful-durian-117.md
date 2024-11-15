2024-06-23 
17:14

Tags : #experiments [[experiments]]

# youthful-durian-117

## Description of the run

This is the first experiment done by Aniketh. There werent any significant changes in the code as such as it was meant as a test. The only major change in the code would be the numeber of epochs.

Number of epochs: 50
Model Used: UNet

## Results

The results arent that impressive. On comparison with the longest run of the model, specifically warm-planet-95, it is evident that longer training times increase the performance of the model.
### validation mean_iou score
The highest validation mean_iou score was for the **MYO** class. An interesting observation is that the classes, LV, RV, AO and PA, the mean_iou scores are similar, (approx. 0.06), and the classes, LA,RA are also in a similar situation(approx. 0.14 and 0.16 respectively).  

### validation dice score
The higesh dice score was for again for the **MYO** class(approx. 0.54). Similar to the earlier case, the classses LV, RV, AO and PA, again have siimilar score in the range of  0.11-0.12. The LA and RA classes again get scores of 0.27 and 0.24 respectively.

### inference on the test split
The metric used in the test evaluation was the dice score. The results are as follows:

Metric on original image spacing: 0.1984
LA: 0.3023
MYO: 0.2881
RA: 0.2416
LV: 0.1832 
AO: 0.1569
PA: 0.1368
RV: 0.1036

The resultsa re interesting as the model did not reflect its performance on the validation dataset. The classwise score calculation was done by taking the average for all the images in the test set. The results are that the LA class has the highest score.

### Comparison with thre 500 epoch run
In the 500 epoch run the class with the highest dice score on validation would is LV. All classes achieve a similar dice score which is around 80-86


# References

[wandb log](https://wandb.ai/amrita-medicalai/vr-heart-segmentation/runs/wrmyezye/overview?nw=nwuseranikethvij464)
