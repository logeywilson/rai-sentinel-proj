# RAI - Sentinel SAR Floodwater Detection

## Description

This project has taken on the task of detecting the presence of floodwater in Sentinel-1 global synthetic aperture radar (SAR) imagery. Flooding is the most frequent and costly natural disaster in the US! High resolution SAR imaging has strengthened monitoring systems by providing data in otherwise inaccessible areas at frequent time intervals. Improving accuracy has the potential for strengthening early warning systems, risk assessment, and target relief.

<img src="https://www.esa.int/var/esa/storage/images/esa_multimedia/images/2014/01/sentinel-1_radar_vision/13494392-1-eng-GB/Sentinel-1_radar_vision_pillars.jpg" width="500">


## Objective

Bin Yu and Rebecca L. Barter's book [__Veridical Data Science__](https://vdsbook.com/) is an excellent resource for those seeking to learn more about how to employ the full data science life cycle (DSLC) when approaching a problem. The goal of this project is for two non-data scientists to practice the implementation of the methods explored in the book on a real-world problem. Since domain knowledge was lacking we leaned heavily on previous work done mentioned in __Resources__ . Empirical metrics to measure the success of models trained are Intersection of Union (IoU) and F1 Score. 

## Approach

In order to get a better understanding of the what Sentinel SAR data looks like, an Exploratory Data Analysis (EDA) was done on data linked [here](https://www.kaggle.com/datasets/salazarslytherin/stac-overflow-microsoftdrivendata-competition). This data allowed us to see interesting features like image location and date. It was helpful to understand how location and time affect flood detection and impact. The overlay of S1 images and their Ground Truth comparisons was helpful in visualizing successful results in prediction.

Once a good understanding of the Sentinel metadata was achieved, the [training data used for models](https://beta.source.coop/repositories/c2sms/c2smsfloods/description/) was downloaded. We decided to use this dataset in the training of our models, since it had been the most updated version with 900 images. EDA on the training data showed side-by-side comparisons of S1 and S2 images with Ground Truth.

We sought to compare the accuracy of three different models on this S1 training data: Unet, Unet++, and LinkNet.  

## Evaluation



## Resources


