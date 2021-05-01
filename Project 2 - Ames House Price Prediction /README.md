# Project 2: Ames House Price Prediction

#### Author: Teo Zhan Rui

This project comprises 2 notebooks,
1) Part 1- Introduction and Preprocessing,
2) Part 2 - Modelling, Prediction and Conclusion.

## Problem Statement

1) Investigate how well the linear regression predicts past prices and recommend applications of model to future sales.
2) Determine the most important fixed features in determining the sale price of a property.
3) Identify the most important features that can be improved by renovation to drive up the property price. Similarly, identify the most undesirable features that are detrimental to property prices.

## Executive Summary

1) The model predicts well for properties of prices up to USD 350,000. Beyond that, the model often under-estimates the price. 

2) Fixed features: Lot area, gross living area and location determine the sale price the most. 
Stone Brook and Northridge Villa are the best neighborhoods. Those in Department of Transport and Rail Road fetch the lowest prices 
Properties near off-site features like parks and greenbelt improve prices while those near the railway are undesirable. Townhouses and properties with high lot frontage are negatively impacted.

3) Renovation: Improvement to kitchen quality can help lift prices. Excessive garage area hurt prices.

**Model Metrics**

Model Selection based on lowest root mean squared error: 

Ridge Regression, alpha=16.1

*Train* <br>
$R^{2}$ score = 0.939 <br>
RMSE = 21758

*Test* <br>
$R^{2}$ score = 0.906 <br>
RMSE = 24414

**suggestions for further analysis**

1) Apply in depth statistical tests to examine violations of assumptions for linear regression such as homoscedasticity. Log normalization of prices has done well to transform data but statistic tests are required for further studies.

2) Filter features that were reduced greatly by ridge regression and also eliminated by lasso regression to improve model. 

3) Remove more correlations with poor correlation to sale price.

4) For higher priced properties, they can be bundled with similarly priced properties from other states of comparable markets for separate modeling to achieve better predictions. 

#### Sources: 
1. https://beacon.schneidercorp.com/Application.aspx?AppID=165&LayerID=2145&PageTypeID=4&PageID=1108&Q=225687783&KeyValue=0905200220
2. https://fred.stlouisfed.org/series/CSUSHPINSA


#### final list of variables after data processing and feature selection:

The list above shows final 139 variables used to train the model grouped into 4 broad categories.

ordinal discrete:
       'lot_shape', 'utilities', 'land_slope', 'overall_qual', 'exter_qual', 'bsmt_qual', 'bsmt_exposure', 'bsmtfin_type_1', 'heating_qc',
       'electrical', 'bedroom_abvgr', 'kitchen_abvgr', 'kitchen_qual', 'functional', 'fireplaces', 'fireplace_qu', 'garage_qual',
       'paved_drive', 'fence', 'mo_sold'

nominal discrete (one hot encoded):

       'ms_zoning_RH', 'ms_zoning_RL', 'ms_zoning_RM', 'ms_zoning_non R', 'street_Pave', 'land_contour_HLS',
       'land_contour_Low', 'land_contour_Lvl', 'lot_config_CulDSac', 'lot_config_FR2', 'lot_config_FR3', 'lot_config_Inside'
       'neighborhood_Blueste', 'neighborhood_BrDale', 'neighborhood_BrkSide', 'neighborhood_ClearCr', 'neighborhood_CollgCr', 'neighborhood_Crawfor',
       'neighborhood_Edwards', 'neighborhood_Gilbert', 'neighborhood_Greens', 'neighborhood_IDOTRR', 'neighborhood_MeadowV', 'neighborhood_Mitchel',
       'neighborhood_NAmes', 'neighborhood_NPkVill', 'neighborhood_NWAmes', 'neighborhood_NoRidge', 'neighborhood_NridgHt', 'neighborhood_OldTown',
       'neighborhood_SWISU', 'neighborhood_Sawyer', 'neighborhood_SawyerW', 'neighborhood_Somerst', 'neighborhood_StoneBr', 'neighborhood_Timber',
       'neighborhood_Veenker', 'condition_1_Feedr', 'condition_1_Norm', 'condition_1_PosA', 'condition_1_PosN', 'condition_1_RRAe',
       'condition_1_RRAn', 'condition_1_RRNe', 'condition_1_RRNn', 'bldg_type_2fmCon', 'bldg_type_Duplex', 'bldg_type_Twnhs',
       'bldg_type_TwnhsE', 'house_style_1.5Unf', 'house_style_1Story', 'house_style_2.5Fin', 'house_style_2.5Unf', 'house_style_2Story',
       'house_style_SFoyer', 'house_style_SLvl', 'roof_style_Gable', 'roof_style_Gambrel', 'roof_style_Hip', 'roof_style_Mansard',
       'roof_style_Shed', 'mas_vnr_type_None', 'mas_vnr_type_Others', 'foundation_CBlock', 'foundation_PConc', 'foundation_Slab',
       'foundation_Stone', 'foundation_Wood', 'central_air_Y', 'garage_type_Attchd', 'garage_type_Basment', 'garage_type_BuiltIn',
       'garage_type_CarPort', 'garage_type_Detchd', 'garage_type_NA', 

continuous:     

        'lot_frontage','lot_area','total_bsmt_sf','gr_liv_area','garage_area','misc_val', 'age','ext_blt_area','total_bath','saleprice'

interaction terms of continuous (polynomial features):
       
       'lot_frontage^2', 'lot_frontage lot_area', 'lot_frontage total_bsmt_sf',
       'lot_frontage gr_liv_area', 'lot_frontage garage_area', 'lot_frontage age', 'lot_frontage ext_blt_area',
       'lot_frontage total_bath', 'lot_area^2', 'lot_area total_bsmt_sf', 'lot_area gr_liv_area', 'lot_area garage_area', 'lot_area age',
       'lot_area ext_blt_area', 'lot_area total_bath', 'total_bsmt_sf^2', 'total_bsmt_sf gr_liv_area', 'total_bsmt_sf garage_area',
       'total_bsmt_sf age', 'total_bsmt_sf ext_blt_area', 'total_bsmt_sf total_bath', 'gr_liv_area^2', 'gr_liv_area garage_area',
       'gr_liv_area age', 'gr_liv_area ext_blt_area', 'gr_liv_area total_bath', 'garage_area^2', 'garage_area age', 'garage_area ext_blt_area',
       'garage_area total_bath', 'age^2', 'age ext_blt_area', 'age total_bath', 'ext_blt_area^2', 'ext_blt_area total_bath', 'total_bath^2'

Please refer to "Part 1- Introduction and Preprocessing.ipynb" for details on selection and engineering process. 