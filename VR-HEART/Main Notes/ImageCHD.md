2024-06-19 01:03

Tags :#[[research]] #research

## Abstract

The dataset consists of CT images from 110 CT images. Each patient falls under in one  of the 16 different types of CHD. Hence there are a total of 17 classes(including the Normal/ Healthy heart structure). 

The paper also discusses the results from a baseline model. 

## Parts of the heart

![[Pasted image 20240619210315.png]]

The heart is segmented into 7 parts, namely:
- Left Ventricle -> LV
- Right Ventricle -> RV 
- Left Atrium -> LA
- Right Atrium -> RA
- Myocardium -> Myo
- Aorta -> AO
- Pulmenary Artery ->PA

Majority of the CHD types arise from the above parts excluding Myo.

## CHDs

CHD - Congenital Heart Disease
There are multiple different types of CHDs, some more uncommon than others.

![[Pasted image 20240619181745.png]]

The difficulty in classification arises from how unique and "separated" each of the parts are in the data. Some CHDs have very similar symptoms in the shape of the heart, making them harder to segment and harder to classify.    

## The Baseline Method

![[Pasted image 20240619183526.png]]

There are two subtasks
 - Segmentation Based Connection Analysis
 - Similarity Based Shape Analysis

### Segmentation Based Connection Analysis 

Consists of two more subtasks
 - Bloodpool segmentation
 - Segmentation of parts of the Greater Arteries and chambers

The blood pool segmentation is to isolate the heart from the rest of the image. Blood pool segmentation essentailly segments regions with high blood density. 

The chambers and GA segmentation is done and sent to the connection analysis module. This module has the function of extracting the connection features between AO/PA (GA) + LV/RV and LV/RV + LA/RA.  

### Similarity Based Shape Analysis




## References 

[ImageCHD: A 3D Computed Tomography Image Dataset for Classification of Congenital Heart Disease](https://arxiv.org/pdf/2101.10799)
