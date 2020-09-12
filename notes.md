# Notes

Main Challenge Page:  
https://xeek.ai/challenges/force-well-logs/overview

98 wells within the training dataset  
10 wells within the open test dataset  
10-20 wells kept in a closed test dataset

## Problem

Prediction of lithofacies from well log measurements.  
Classification problem

## The Data

The following well curves are present:  
- DEPT **Always present**
- CALI
- RDEP (Deep Res)
- RHOB
- DHRO 
- SGR
- GR **Always present**
- RMED (Med Res)
- RMIC (Mic Res)
- NPHI
- PEF
- RSHA (Shallow Res)
- DTC
- SP
- BS
- ROP
- DTS
- DCAL
- MUDWEIGHT
- X_LOC
- Y_LOC
- Z_LOC (TVDSS)

Additional Curves:
- FORCE_2020_LITHOFACIES_CONFIDENCE (1: high, 2: medium, 3: low)

Target Curve:
- FORCE_2020_LITHOFACIES_LITHOLOGY

Missing data is represented by NaN

## Lithology Key

|Number|Lithology|
|------|---------|
|30000 |Sandstone|
|65030 | Sandstone/Shale |
|65000 | Shale|
|80000 | Marl |
|74000 | Dolomite |
|70000 | Limestone |
|70032 | Chalk |
|88000 | Halite |
|86000 | Anhydrite |
|99000 | Tuff |
|90000 | Coal |
|93000 | Basement |

## Modelling Strategies to Consider:
- Petrophysical workflow
- Bad data identification
- Consider stratigraphy - although would be better to learn without it
- Predicting lithostratigraphy based on the log measurements
- Incorporating key information from rare well logs is a challenge
-  Consider building sub-models to handle situations when key curves are absent
- Lithofacies boundary is often subjective and may be imprecise - consider weighting the samples either side of the boundary to a lower weighting