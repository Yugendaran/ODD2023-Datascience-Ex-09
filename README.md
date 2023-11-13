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


## OUPUT

![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/90628c64-0cd7-488e-ad19-942a60a026be)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/c01720f4-3efb-4c6f-b6b8-904240da18ec)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/80c3d519-bbe2-4cd7-801b-162c003be5b4)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/8ea9a521-cf2e-4058-b901-804285e260bc)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/148a04d6-867b-49e8-8fd8-0434281d59bb)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/b7ce2854-76f7-4bb9-8984-4aedb213218c)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/0aa92af3-a211-41c8-a896-8fcf2c9a089a)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/b5f10bf8-fc56-4f3c-8c7d-72a65dc64198)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/e48a47fb-c79f-4c32-8416-9c58340d9a84)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/23e0738c-bbed-4abf-9e71-ffe9ba9ba21e)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/4bfae666-539f-4ffb-91e0-ce27a75cb3c8)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/04a7648b-a509-4b08-b27e-afd43be67340)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/7804a8b9-d6f0-4497-9401-6cd253fef56c)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/a8de64e9-695e-4606-9b1c-3013fb5fe0ce)
![image](https://github.com/Yugendaran/ODD2023-Datascience-Ex-09/assets/128135616/6aec5757-3801-4317-8ee5-047f3e62ab51)





## Result:
Thus, Data Visualization on a complex dataset and save the data to a file has been performed successfully.















