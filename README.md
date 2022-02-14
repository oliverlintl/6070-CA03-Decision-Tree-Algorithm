# 6070 CA03: Decision Tree Algorithm
![alt text](image/tree.jpg)

## Objective
The objective of this case is to train a decision tree to predict if a individual's income would be above or below $50,000 based on some attributes about them such as their race, sex, education and work class etc. There are a total of 48842 records in this dataset.

## Data
The data is collected from the US Census Bureau's American Community Survey. All data has been divided into bins because the decision tree model is not able to be trained with continuous data. 
The data contains the following columns:
>hours_per_week_bin: Hours Worked per Week  <br>
>occupation_bin: Occupation Category <br>
>msr_bin:	Marriage Status & Relationships      <br>
>capital_gl_bin:  Capital Gain/Loss	      <br>
>race_sex_bin: Race-Sex Group	      <br>
>education_num_bin: Number of Years of Education	      <br>
>education_bin: Education Category  	      <br>
>workclass_bin: Work Class	      <br>
>age_bin: Age	      <br>
>flag: Train or Test	      <br>
>y: ('>50K' and '<=50K') [Labels: 1, 0]
![alt text](image/data.jpg)

## Tranforming the Data
To fit the decision tree we need to first transform the data from string categories into float categories. This is because the decision tree model cannot take strings as input. We use OrdinalEncoder from category_encoders to accomplish that. 
```ruby
import category_encoders as ce
encoder = ce.OrdinalEncoder(cols = x_cols)
X_train = encoder.fit_transform(X_train)
X_test = encoder.transform(X_test)
```
