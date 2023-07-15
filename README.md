# My-4th-Capstone - Liver Disease Early Detection

My Role:
As a Junior AI Engineer employed at a Healthcare Company, I am currently engaged in a project assigned by the Lab Department of the Ministry of Health (MOH). Our objective is to develop a cost-effective (aka cheap) machine learning algorithm known as the "Liver Disease Early Detection Program".

The dataset (from UCI Machine Learning) comprises 416 records of patients with liver disease and 167 records of patients without liver disease.
It was collected from the northeastern region of Andhra Pradesh, India.
The "Liver Disease" column serves as a class label to categorize the patients into two groups: those with liver disease and those without.
Among the patients, there are 441 males and 142 females.
If a patient's age surpasses 89, their age is recorded as "90."

01. [Age] Age of the patient
02. [Gender] Gender of the patient
03. [TB] Total Bilirubin
04. [DB]	Direct Bilirubin
05. [Alkphos] Alkaline Phosphatase
06. [Sgpt] Alamine Aminotransferase
07. [Sgot] Aspartate Aminotransferase
08. [TP] Total Protiens
09. [ALB] Albumin
10. [A/G Ratio] Albumin and Globulin Ratio
11. [Liver Disease] Selector field used to split the data into two sets (labeled by the experts)

### 1. Libraries
- Includes: pandas, numpy, matplotlib, seaborn and sklearn

### 2. Explore the dataset
- Load the dataset.<br>
- Add headers.

### 3. Data Cleaning
- Remove any duplicate data <br>
- Checking for empty data cells, remove rows (if any). <br>
- Change column "Liver Disease" data, from original '2' into '0'. <br>
- Change column "Gender", from original "Male" / "Female" into numericals "0" / "1". <br>
- Dataset final check - after Data Cleaning <br> 

### 4. Dataset Visualization
- Histogram Features <br>
![](https://i.imgur.com/whIFNMM.jpg)

- Correlations Heatmap <br>
![](https://i.imgur.com/GF6tZ5e.jpg)
Note: Correlation value between -1 and 1. <br>
There is multicollinearity between :
- 'TB' and 'DB' is 0.98.
- 'Sgpt' and 'Sgot' is 0.84.
- 'TP' and 'Albumin' is 0.80.
- 'ALB' and 'AG_Ratio' is 0.75
Drop DB, and keep TB, as multicollinearity is above 0.85.
<br>

### 5. Running the classifier
- Generate the Classification Report
- Generate the Confusion Matrix
![](https://i.imgur.com/kxcUv7b.jpg)

### 6. Evaluate models
- Compare Accuracy, Recall, Precision, and F1 Scores.<br>
![](https://i.imgur.com/RxlA6fR.jpg) <br> <br>
- Compare ROC (Receiver Operating Characteristic) graphs <br>
![](https://i.imgur.com/9thCjZS.jpg)<br> <br>
- Compare AUC - Area Under ROC Curve<br>
![](https://i.imgur.com/rv0LwG8.jpg)<br> <br>

### 7. Insights
- Due to the small size of the dataset (553 observations) and its mild class imbalance, with the minority class (class 0) accounting for approximately less than 30%, the model performances are expected to vary. Furthermore, the number of positive records is three times higher than the number of negative records.<br>
- The classification report shows accuracy scores ranging from approximately 77% to 81% for all three models, with the highest score achieved by KNN. However, since our goal is to **capture all positive cases (True Positive + False Positive)** in this scenario, we should **prioritize the Recall score** when selecting a model for prediction. According to the Recall score, Logistic Regression performs the best with an accuracy of 92.86%.<br>
- When examining the ROC graphs, reducing the thresholds value will allows us to capture all False Negatives (FN). The AUC score indicates that the Random Forest model is the best model for prediction. However, since our focus is on capturing all positive cases rather than accurately ranking predictions, the AUC score is not a useful metric for this specific prediction ranking.<br>

### 8. Bonus Round
![](https://i.imgur.com/XTacZ0x.jpg)








