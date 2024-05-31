# RAI - Sentinel SAR Floodwater Detection

## Description

This project has taken on the task of detecting the presence of floodwater in Sentinel-1 global synthetic aperture radar (SAR) imagery. Flooding is the most frequent and costly natural disaster in the US! High resolution SAR imaging has strengthened monitoring systems by providing data in otherwise inaccessible areas at frequent time intervals. Improving accuracy has the potential for strengthening early warning systems, risk assessment, and target relief.

<img src="https://www.esa.int/var/esa/storage/images/esa_multimedia/images/2014/01/sentinel-1_radar_vision/13494392-1-eng-GB/Sentinel-1_radar_vision_pillars.jpg" width="500">
[Credit: ESA/ATG medialab]


## Objective

Bin Yu and Rebecca L. Barter's book [__Veridical Data Science__](https://vdsbook.com/) is an excellent resource for those seeking to learn more about how to employ the full data science life cycle (DSLC) when approaching a problem. The goal of this project is for two non-data scientists to practice the implementation of the methods explored in the book on a real-world problem. Since domain knowledge was lacking we leaned heavily on previous work done mentioned in __Resources__ . Empirical metrics to measure the success of models trained are Intersection of Union (IoU) and F1 Score. 

## Approach

In order to get a better understanding of the what Sentinel SAR data looks like, an Exploratory Data Analysis (EDA) was done on data linked [here](https://www.kaggle.com/datasets/salazarslytherin/stac-overflow-microsoftdrivendata-competition), showing 542 images from 13 global flood events (512x512 pixel). This data allowed us to see interesting features like image location and date. It was helpful to understand how location and time affect flood detection and impact. The overlay of Sentinel-1 (S1) images and their Ground Truth comparisons was helpful in visualizing successful results in prediction.

Once a good understanding of the Sentinel metadata was achieved, the [training data used for models](https://beta.source.coop/repositories/c2sms/c2smsfloods/description/) was downloaded. We decided to use this dataset in the training of our models, since it had been the most updated version with 900 images from 18 global flood events (512x512 pixel). EDA on the updated training data showed side-by-side comparisons of S1 and S2 images with Ground Truth. The training data used for our models however only considered S1 images.

We sought to compare the accuracy of three different models on this S1 training data: Unet, Unet++, and LinkNet. We came to the conclusion that the comparison of different neural network architectures would be a beneficial in understanding how they each perform on updated S1 data. Our idea for this approach came from the paper: ["C2A-DC: A context-aware adaptive data cube framework for environmental monitoring and climate change crisis management"](https://www.sciencedirect.com/science/article/pii/S2352938524000351).

### exploratory_data_analysis
EDA on Sentinel SAR data with 542 images.

### training_base_Unet
EDA on Sentinel SAR data with 900 images. Shows preparation of training data and segmentation approach using neural network with the Unet architecture.

### training_base_Unet++
Shows preparation of training data and segmentation approach using neural network with the Unet++ architecture.

### training_base_Linknet
Shows preparation of training data and segmentation approach using neural network with the Linknet architecture.

## Evaluation
The global IoU and F1 Score were considered below:

### _Unet_
- _IoU_: 0.7451
- _F1 Score_ : 0.8539

### _Unet++_
- _IoU_:
- _F1 Score_ :

### _Linknet_
- _IoU_:
- _F1 Score_ :

 _insert model name_ came out on top! Our IoU and F1 Scores are below what was hoped, but with the incorporation of the following we believe it could be improved:
- Elevation data --> The use of [NASADEM](https://www.earthdata.nasa.gov/esds/competitive-programs/measures/nasadem), as shown in the [first-place solution](https://github.com/sweetlhare/STAC-Overflow) to the "Map Floodwater from Radar Imagery" competition, is extremely helpful in determining which areas are likely to flood. The reasoning is that areas with lower elevation have a higher likelihood of flooding. 
- Precipitation data --> The use of NASA's [GPM and TRMM data](https://gpm.nasa.gov/data) to examine precipitation could also help determine likelihood of flooding since areas with high precipitation are also subject to flooding.
- The use of trained ML models to solve the binary classification problem on pixel-by-pixel data. This is a helpful addition since it does not involve the creation of a complex neural network! One implementation example is shown in the [first-place solution](https://github.com/sweetlhare/STAC-Overflow).

On the topics of real-world impacts, it was mentioned that Flood Disaster is among the most costly natural disasters in the world. In the US Spe


## Resources
- [__Veridical Data Science__](https://vdsbook.com/)
- [Map Floodwater from Radar Imagery Competition](https://www.drivendata.org/competitions/81/detect-flood-water/)
- ["C2A-DC: A context-aware adaptive data cube framework for environmental monitoring and climate change crisis management"](https://www.sciencedirect.com/science/article/pii/S2352938524000351)
- ["LinkNet: Exploiting encoder representations for efficient semantic segmentation"](https://ieeexplore.ieee.org/document/8305148)
- ["U-Net: Convolutional Networks for Biomedical Image Segmentation"](https://arxiv.org/abs/1505.04597)
- ["Daytime Arctic Cloud Detection Based on Multi-Angle Satellite Data With Case Studies"](https://www.researchgate.net/publication/4742960_Daytime_Arctic_Cloud_Detection_Based_on_Multi-Angle_Satellite_Data_With_Case_Studies)
- [Cost of Flooding in the U.S.(NOAA)](https://www.ncei.noaa.gov/access/monitoring/dyk/billions-calculations)
- ["Evaluating the Economic Cost of Coastal Flooding"](https://www.aeaweb.org/articles?id=10.1257/mac.20180366)
