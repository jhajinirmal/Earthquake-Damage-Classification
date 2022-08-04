### Earthquake Damage Classification

The Goal of this project is to classify building into different damage grade classes (Ranging from 0 to 4) based upon the building characteristics like 
height, number of floors, plinth area, building material, foundation time, material used in superstructure etc.

The data for this project has been obtained from [this website](https://eq2015.npc.gov.np/). 

The data had more than 700,000 rows which after cleaning and feature engineering is divided into 3 parts. 64% data is used to train, 16% is used for 
validation and 20% is used to test the final model.

Preprocessing, Exploration and feature engineering is done in a separate notebook. Different models are tried and tuned in a different notebook and then 
in a separate notebook, the final model is built.

In this project, **NVIDIA RAPIDS** libraries (cudf, cuml, cup) are used along with Pandas, numpy, Sklearn etc. This is to train the models on a GPU which 
makes the process faster.

The different algorithms and their train and validation accuracy are:

                          
| Algorithm      | Training Score |  Validation Score |
| -----------    | -----------    |     ------------  |
| Random Forest  | 0.63          |     0.55              |
| KNN      | 0.60           |        0.57           |
| XGBoost  | 0.70           |        0.57           |

Thgough XGBoost and KNN had same validation score, KNN had lower training score. This means that KNN model has lower variance. So, KNN is used over XGBoost
to make the final model.

The test score is 0.57.
