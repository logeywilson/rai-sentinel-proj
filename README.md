# RAI - Sentinel SAR Floodwater Detection

## Description

This project has taken on the task of detecting the presence of floodwater in Sentinel-1 global synthetic aperture radar (SAR) imagery. Flooding is the most frequent and costly natural disaster in the US! High resolution SAR imaging has strengthened monitoring systems by providing data in otherwise inaccessible areas at frequent time intervals. Improving accuracy has the potential for strengthening early warning systems, risk assessment, and target relief.

<img src="https://www.esa.int/var/esa/storage/images/esa_multimedia/images/2014/01/sentinel-1_radar_vision/13494392-1-eng-GB/Sentinel-1_radar_vision_pillars.jpg" width="500">


## Objective

Bin Yu and Rebecca L. Barter's book [__Veridical Data Science__](https://vdsbook.com/) is an excellent resource for those seeking to learn more about how to employ the full data science life cycle (DSLC) when approaching a problem. The goal of this project is for two non-data scientists to practice the implementation of the methods explored in the book on a real-world problem. Since domain knowledge was lacking we leaned heavily on previous work done mentioned in __Resources__ . Empirical metrics to measure the success of models trained are Intersection of Union (IoU) and F1 Score. 

## Approach

In order to get a better understanding of the what Sentinel SAR data looks like, an Exploratory Data Analysis (EDA) was done on data linked [here](https://www.kaggle.com/datasets/salazarslytherin/stac-overflow-microsoftdrivendata-competition), showing 542 images from 13 global flood events (512x512 pixel). This data allowed us to see interesting features like image location and date. It was helpful to understand how location and time affect flood detection and impact. The overlay of S1 images and their Ground Truth comparisons was helpful in visualizing successful results in prediction.

Once a good understanding of the Sentinel metadata was achieved, the [training data used for models](https://beta.source.coop/repositories/c2sms/c2smsfloods/description/) was downloaded. We decided to use this dataset in the training of our models, since it had been the most updated version with 900 images from 18 global flood events (512x512 pixel). EDA on the updated training data showed side-by-side comparisons of S1 and S2 images with Ground Truth. The training data used for our models however only considered S1 images.

We sought to compare the accuracy of three different models on this S1 training data: Unet, Unet++, and LinkNet.  

## Evaluation
The global IoU and F1 Score were considered below:

_Unet_ --> _IoU_:   _F1 Score_ :
_Unet++_ --> _IoU_:   _F1 Score_ :
_Linknet_ --> _IoU_:   _F1 Score_ :

 _insert model name_ came out on top! Our IoU and F1 Score are far below what was hoped but with the incorporation of the following we believe it could be improved:
- Elevation data --> The use of NASADEM, as shown in the [first-place solution](https://github.com/sweetlhare/STAC-Overflow) to the "Map Floodwater from Radar Imagery" competition, is extremely helpful in determining which areas are likely to flood.
- Rainfall data -->


## Resources


