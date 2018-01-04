# Soil

## Table of Contents

[Study Description](#intro)    
[Feature Relationship to Culture Status](#importance)    
[Feature to Feature](#workflow)    
[Clustering](#quickstart)    
[Cross Validation](#install)    
[(Exploratory) Balancing the Data](#usage)     

## <a name="intro"></a>Study Description

This exploratory analysis examines the relationship between soil characteristics and non-tuberculosis mycobacterial (NTM) culture status with the explicit goal of identifying soil features that promote NTM growth and clinical susceptibility. The data in this preliminary analysis contains 52 soil samples with cooresponding NTM culture status. 

## <a name="importance"></a>Feature Relationship to Culture Status

A non-parametric wilcoxon-rank sum test is used to calculate the relationship between the soil characteristics and NTM culture status. Of the 16 soil characteristics only three passed as significant below a p-value of 0.05. Goethite was near significance with a p-value of 0.0584. The test rejected the null hypothesis that the distribution of soil characteristics came from the same populations. 

| Soil Category    | Culture p-value                                    |
|------------|-------------------------------------------------|
| Maghemite | 0.0317 \* |
| Halloysite  | 0.0038 \** |
| Kaolinite | 0.0196 \* |

Below are the plots showing the directionality of the relationship between the three significant soil characteristics. 

#### Maghemite by Culture Status

<img src="https://github.com/glickmac/Soil/blob/master/images/download-1.png" height="400" width="550">

#### Halloysite by Culture Status

<img src="https://github.com/glickmac/Soil/blob/master/images/download-2.png" height="400" width="550">

#### Kaolinite by Culture Status

<img src="https://github.com/glickmac/Soil/blob/master/images/download-3.png" height="400" width="550">

## <a name="workflow"></a>Feature to Feature

In addition to comparing the features to the response variable, the relationship between features was examined in full. The correlation plot below displays significant relationships between features. The boxes without an X indict a significant correlation between features.<font color="red"> Red bubbles </font> indicate a negative relationship, whereas <font color="blue"> blue bubbles </font> signify a positive relationship. 

<img src="https://github.com/glickmac/Soil/blob/master/images/download-4.png" height="500" width="700">

## <a name="quickstart"></a>Clustering

The tree below demostrates that the culture positive group does not cluster well together with the current features. Feature select may change this distance based clustering. 

<img src="https://github.com/glickmac/Soil/blob/master/images/download-5.png" height="500" width="800">


## <a name="install"></a>Cross Validation

To identify important features, we perform cross-validation on the dataset. The table below details the error rate as the number of features is halved. The lower the error rate the better. 

| Number of Features    | Error Rate                                  |
|------------|-------------------------------------------------|
| 16 | 0.231 |
| 8  | 0.173 |
| 4 | 0.192 |
| 2 | 0.192 |
| 1 | 0.269 |

The error rate below 0.2 suggests that some features are informative against the response variable. The optimal number of features in a reduced set would be around 8 as suggested by the performance table above. 

#### Random Forest Feature Selection

Below is a table with the top 8 feature importance scores from a random forest enseamble algorithm. The higher the value, the more important the feature. 

| Soil Category   | Gini Importance Measure                            |
|------------|-------------------------------------------------|
| Kaolinite | 1.76 |
| Maghemite  | 1.69 |
| Halloysite | 1.64 |
| Goethite | 1.42 |
| Magnetite | 1.31 |
| Ilmenite  | 1.20  |
| Gibbsite  | 1.05  |
| Kaolin_Group  | 1.00  |


We performed feature selection to reduce the number of features from 16 to the top 8 listed above. Then we performed a cross-validation error rate analysis as before. The results are listed in the table below. 

| Number of Features    | Error Rate                                  |
|------------|-------------------------------------------------|
| 8  | 0.154 |
| 4 | 0.212 |
| 2 | 0.173 |
| 1 | 0.250 |

The performance with the reduced feature set averaged 0.197 compared with the full dataset at the same levels of 0.2065 or a 5% improvement in performance. 


