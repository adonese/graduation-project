# GeoidApp: A Unified Framework for Geoid Computations
---
This is our thesis for BSc at University of Khartoum.

## Thesis Objectives

  - Evaluation of recent GRACE/GOCE models on Sudan terrestrial data to derive a new reference surface
  - Developing a software for that purpose

## Study area
We have two different datasets correspond to two different geographic locations. The first dataset is an astrogeodetic datasets computed by Adam (1967). Adam (1967) has collected 46 points among Sudan.
The second dataset is a GPS/leveling datasets consist of 24 points distributed among Khartoum state.

## GGM
Global Geopotential Model is a mathematical function that describes the gravity field of the Earth in a 3-dimensional space. Three different **dedicated satellite missions** are used to obtain coefficients to be used later to derive a new reference surface for the study area.

### Dedicated Satellite missions
- CHAMP (CHAllenging Mini Payload)
- GRACE (Gravity Recovery and Climate Experience)
- GOCE (Gravity Field and Steady-State Ocean Circulation Explorer)

We have only used data from GRACE and GOCE for our study.

| Model Name | Release Data | Max Degree/Order|
|---         |---           |---              |
|ITU_GGC16   |2016          |250              |
|ITU_GRACE16 |2016          |180              |
|GECO        |2015          |2190             |
|EGM2008     |2008          |2190             |
|EIGEN-6C4   |2014          |2190             |

Each model has different degrees (ranging from 0 to max_degree), each degree corresponds to a different half wavelength. The thing to care about too much is that, each degree will have roughly different results (though our study shows that higher degrees tend to have the same results)

## Similar works

Historically there are three datums for Sudan. The first one was proposed by Fashir (1991) and it has an accuracy of 1.8m. Ahmed (2008) has conducted a study to compute a new datum based on KTH-method. They show an accuracy of 0.576m on the same GPS/leveling dataset that we used. More recently, WalyEldeen (2015) proposed a new datum for Sudan with an accuracy of 0.644m on the same GPS/leveling dataset using Least square collocation.

Our results have shown an improvement of 37% compared to Ahmed (2008) and 43% compared to WalyEldeen (2015).

|Work (Year) | STD[m]   | GGM used|
|---           |---       |---     |
|Ahmed (2008)  | 0.576  |EIGEN-GRACE02S |
|WalyEldeen (2015)| 0.64 | GO_CONS_GCF_2_TIM_R4 (TIM-R4) |
|GeoidApp (2016) | 0.365 | ITU_GGC16 |
