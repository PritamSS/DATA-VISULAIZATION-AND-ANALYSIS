
# DATA ANALYSIS OF HEART PATIENTS
Data analysis is a vast field with innumerable real-world applications. In this project the aim is to select a dataset and analyze the data which is useful to gain an insight about the dataset.

Some Data visualization techniques were applied and inferences about the daatset were drawn

Finally, predictive models were built using some standard machine learning algorithms and their accuracies compared.





## Dataset Overview

The dataset was obtained from [Kaggle](https://www.kaggle.com/fedesoriano/heart-failure-prediction). The dataset chosen was on heart disease with 918 datapoints with 11 attributes which are likely to be a factor and here we try to determine how different parameters determine whether the patient under consideration is positive.

### Context
People with cardiovascular disease or who are at high cardiovascular risk (due to the presence of one or more risk factors such as hypertension, diabetes, hyperlipidaemia or already established disease) need early detection and management wherein a machine learning model can be of great help.


### Sample Dataset

![df](https://drive.google.com/uc?export=view&id=10OdLM41_8Mt_IeofxmmY5QKWv2ULcvIt)



## Data Cleaning And Preprocessing
The following two operations were performed under data cleaning:
1.	Ignoring rows with wrong values: 
The column of cholesterol had some values as 0 which is not possible and hence those rows were deleted, 172 rows were deleted finally.
```bash
  df = df_heart_2[df_heart_2.Cholesterol != 0]
```

2.	Changing the string values to integers:
Some attributes have string values such as ChestPainType where [TA: Typical Angina, ATA: Atypical Angina, NAP: Non-Anginal Pain, ASY: Asymptomatic]

All these values were replaced with integer values in the above case with 0, 1, 2, 3 so that analysis can be done later

```bash
j = 0
for i in df_heart['ChestPainType'].unique():
  df_heart_2['ChestPainType']=df_heart_2['ChestPainType'].replace(i, j)
  j = j+1
```
This was repeated for all the string type attributes


## Plots
Different method of data visualization were employed some of them are shown below. To refer all the plots please take a look at the [DATA_VISUALIZATION](https://github.com/PritamSS/DATA-VISULAIZATION-AND-ANALYSIS/blob/main/DATA_VISUALIZATION.ipynb) file
### Box Plots
![box plot](https://drive.google.com/uc?export=view&id=1QlSgFF4tdgkG88w2Ev3nPp4en-fzQyyR)

Inferences:  
For positive subjects following are the inferences drawn:  
???	The median cholesterol levels are higher  
???	The median resting blood pressure is higher  
???	The median Max heart rate is lower

### Heat Maps
![heat maps](https://drive.google.com/uc?export=view&id=1LqgoQ4HP_yiHSEujcwwyhj8Hlq8xtwf0)
Inferences:  
???	We can observe negative correlation between 'Age' and 'MaxHR' i.e younger people have higher heart rate compared to old people  
???	'HeartDisease' and 'Oldpeak' have a positive correlation  

### Violin Plots
![Violin](https://drive.google.com/uc?export=view&id=1k-2YRxciPFi9I9UTHPLdngwCVYO5a75M)

Inferences:  
The following were the inferences drawn are similar to box plot but the addition of KDE gives the following insight:  
???	Most positive patients have resting BP around 140  
???	Most positive patients have MaxHR around 120  
???	Most positive patients are around the age of 60  


## Predictive Models
Standard Machine Learning models were used and this dataset was fitted and their accuracies were compared. The following were the models used


| Model  | Accuracy |
| ------------- | ------------- |
| Logistic regression  | 86.1 %  |
| Decision tree classifier  | 84.5 %  |
| Random forest classifier  | 83.4 %  |

Refer the [DATA_ALGOS](https://github.com/PritamSS/DATA-VISULAIZATION-AND-ANALYSIS/blob/main/DATA_ALGOS.ipynb) file for this code

## Contributors

[Pritam Suttraway](https://github.com/PritamSS)  
[Aruna Jayarajan](https://github.com/Aruna-Jayarajan)
