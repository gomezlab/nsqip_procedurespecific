# nsqip_procedurespecific
Predict procedure specific outcomes from the NSQIP database using neural networks and logistic regression

This repository accompanies the manuscript "Differential Performance of Machine Learning Models in Prediction of Procedure Specific Outcomes". The data used in this project is from the American College of Surgeons NSQIP database (https://www.facs.org/quality-programs/acs-nsqip/participant-use). Data is not posted with this repository due to the ACS NSQIP data use agreement, but researchers at NSQIP-participating hospitals can download the data from the referenced website.

Before using the pre-processing notebooks, the procedure-specific files must be merged with the larger NSQIP participant user files. This can be done using the code in "combine.ipynb". This uses csv files, which can be created from the txt files downloaded from NSQIP by converting them in Microsoft Excel. "Preproc" files exist for each of the studied procedures. These files perform feature engineering, imputation, encoding, and normalization and generate csv files which can then be used in the respective "crossval" notebooks.

The crossval notebooks build NN and LR models using keras and sklearn respectively. They create mean tpr/fpr and precision/recall variables that can be used in the "curves1" to generate ROC and PRC curves.

The shap notebooks create NN models using only procedure-specific variables and use SHAP to identify feature importance values.

The colectomy notebooks are annotated and contain code explanations that are generalizable across all procedures.
