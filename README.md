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

## <a name="install"></a>Cross Validation


#### Required arguments:

| Option     | Description                                     |
|------------|-------------------------------------------------|
| **-s**   | SRR acession number from SRA database           |
| **-o**   | Folder to be used for pipeline output |

#### Optional arguments:

| Option    | Description |
|-----------|-------------|
| **-f**    |FASTA file containing viral sequences to be used in construction of a BLAST database. If neither this argument nor -b are used, ViruSpy will default to using the Refseq viral genome database.|
| **-b**    |BLAST database with viral sequences to be used with Magic-BLAST. If neither this argument nor -f are used, ViruSpy will default to using the Refseq viral genome database.|
| **-d**    |Determines signature of viruses that are integrated into a host genome (runs the BUD algorithm)|

## <a name="usage"></a>(Exploratory) Balancing the Data


