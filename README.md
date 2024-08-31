# Diabetes-BRFSS-DP

This is an anonymized (to support the double-blind review process) code repository for the paper "Enhancing Fairness and Accuracy in Diagnosing Type 2 Diabetes in Young Population". 
This paper is currently under review at IEEE BHI 2024. 

The codes are cleaned and organized into code blocks with proper titles that are easy to follow and can be reproduced. 
### Data:
In paper uses a public dataset which is available at: https://www.cdc.gov/brfss/annual_data/annual_data.htm

### Coding environment:
Python 3.6 has been used to run the codes. Please check the requirements_py3.6.txt for all the libraries with specific versions. Jupyter notebook is used for implementing code. 

Code description:
### 1. BRFSS_data_processing.ipynb
This is the first code segment used for data processing. BRFSS dataset is downloaded and loaded in a raw format. This code extracts the diabetes cohort with the required feature set from the dataset. Additionally, the features are mapped into different categories and later covered in one-hot encoding for machine learning model training. This code process the BRFSS dataset from years 2021, 2019, 2017, and 2015.

### 2. BRFSS_Training_ML_DP.ipynb
This code is used for different model training. This code file is large as it contains 6 machine learning models such as multi-layer perception (MLP), Random Forest (RF), K nearest neighbours (KNN), AdaBoost (AB), Logistic regression (LR), and Naive Bayes (NB) with 9 resampling techniques such as SMOTE, ADASYN, ENN, Random oversampling, Random under-sampling, Near miss, Tomek-links, No-resampling, and Double prioritized sampling (DP). This file contains the code for the 4-year dataset which are 2021, 2019, 2017, and 2015. So in total, this code file contains 6 (ML models) x 9 (resampling) x 4 (datasets) = 216 experiments, each containing 22 subgroup performance analyses. 
Due to the large code file, it might not load online. In that case, it is advised to download the code offline for usage. 

### 3. BRFSS_Subgroup_performance_analysis.ipynb
The previous code already includes the subgroup performance analysis with training codes; however, this code only contains performance analysis and feature importance analysis. 

### 4. BRFSS_Subgroup_threshold_calculation.ipynb
This code is used to analyze the performance of each subgroup with their specific thresholds instead of the whole group threshold which performs better and is used in the main experiment. 

### 5. Separate_group_training.ipynb
This code is used to analyze the performance if models are trained only on subgroups instead of whole groups or resampled whole groups. The performance is lower compared to DP-whole group training.

### 6. Separate_group_training_Heat_map.ipynb
This is the code to generate heat maps for subgroup performance visualization.

## Results

### Baseline Model performance:
![alt text](https://github.com/PiasTanmoy/Diabetes-BRFSS-DP/blob/main/BRFSS%20base%20model%20performance.png?raw=true)

### Proposed DP model performance (improved for age group 30-44):
![alt text](https://github.com/PiasTanmoy/Diabetes-BRFSS-DP/blob/main/BRFSS%20proposed%20DP%20model%20performance.png?raw=true)



