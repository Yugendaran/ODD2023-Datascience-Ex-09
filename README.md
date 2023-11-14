# Ex-09-Data-Visualization-


## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

## Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


## CODE
DEVELOPED BY : YUGENDARAN.G

REGISTER NO : 212221220063
```
import seaborn as sns
import pandas as pd
import matplotlib.pyplot as plt

df=sns.load_dataset("tips")
print(df)

df.isnull().sum()

## 1.Which day of the week has the highest total bill amount?
plt.figure(figsize=(5,5))
plt.title("data with outliners")
df.boxplot()
plt.show()

## 2.What is the average tip amount given by smokers and non-smokers?
plt.figure(figsize=(5,5))
cols=["size","tip","total_bill"]
q1=df[cols].quantile(0.25)
q3=df[cols].quantile(0.75)
iqr=q3-q1
df=df[~((df[cols]<(q1-1.5*iqr))|(df[cols]>(q3+1.5*iqr))).any(axis=1)]
plt.title("dataset after removing outliners")
df.boxplot()
plt.show()

## 3.How does the tip percentage vary based on the size of the dining party?
sns.barplot(x=df["day"],y=df["total_bill"],hue=df["day"])
plt.legend(loc="center")
plt.title("highest total bill amount by day of the week")

## 4.Which gender tends to leave higher tips?
sns.boxplot(x=df["smoker"],y=df["tip"],hue=df["smoker"])
plt.title("average tip amount given by smokers and non-smokers")

## 5.Is there any relationship between the total bill amount and the day of the week?
df["tip_percent"]=df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'], y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")

## 6.How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?
sns.boxplot(x=df["sex"],y=df["tip"],hue=df["sex"])
plt.title("tips based on gender")

## 7.Which dining party size group tends to have the highest average total bill amount?
sns.scatterplot(x=df["day"],y=df["total_bill"],hue=df["day"])
plt.legend(loc="best")
plt.title("total bill amount by day of te week")

## 8.What is the distribution of tip amounts for each day of the week?
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
plt.show()

## 9.How does the tip amount vary based on the type of service (lunch vs. dinner)?
sns.barplot(x=df["size"],y=df["total_bill"],hue=df["size"])
plt.title("average total bill amount by dinning party size")
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()

## 10.Is there any correlation between the total bill amount and the tip amount?
sns.violinplot(x="time",y="tip",data=df)
plt.title("tip amount time of day")
sns.scatterplot(x="total_bill",y="tip",data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```

## OUPUT:

![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/2bc5235b-6898-4a38-b433-0058ade920da)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/53106ab2-654b-4c3d-ba9a-0fe3f5f16413)

![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/a1d15c62-e565-407a-aedc-f406f3b46db0)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/bd89098f-28f0-47ce-abd1-abc0273f7a21)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/34e8bcc1-0676-4d10-9333-3d5da56c5fc9)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/50b118e0-c3a8-4397-8733-c87136d95d0f)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/a0740b65-63e4-4a2b-acf7-eafba79f597e)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/f7c330c9-dc0e-4cf0-ad0f-4c67465552ef)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/58994992-5bfe-4ffd-89d1-0ba79dc8434b)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/be5429cc-1b02-41d7-8531-ccc369d5a4ca)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/4eb55bea-cd59-4c4a-a15e-0ff09f7e306f)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/d4b36e6f-35bf-46c2-998d-3dbbd860c723)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/98749810-1709-427e-acb8-d5b83795c6ee)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/8d150be7-5abb-4749-a404-8bb8afee30e7)


## Result:
Thus, Data Visualization on a complex dataset and save the data to a file has been performed successfully.


