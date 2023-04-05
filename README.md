# workshop-Multivariate-analysis
# AIM:
To Perform Multivariate Analysis
# ALGORITHM:
1.Read the given data

2.Get information from the data

3.Perform the Multivariate Analysis

4.Save the clean data to file
# PROGRAM:
```
Name:KIRUTHIKA S
Regno:212221040085
```
```
import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

import io

from google.colab import files

uploaded = files.upload()

dd = pd.read_csv(io.BytesIO(uploaded['FlightInformation.csv.csv']))

print(dd)
```
# Types of bivariate:
# 1. Numerical & Numerical
```
sns.scatterplot (dd['Date_of_Journey'],dd['Dep_Time'])
```
![image](https://user-images.githubusercontent.com/128348968/230006331-8683e88a-fa65-44cf-8799-066f0407dde4.png)
# 2. Numerical & Categorical
```
sns.barplot (x=dd['Duration'],y=dd['Price'])
```
![image](https://user-images.githubusercontent.com/128348968/230006537-2d958ef7-1824-4fcd-806a-82a9fef9c68d.png)
```
sns.barplot(x=dd["Arrival_Time"],y=dd["Price"],data=dd)
```
![image](https://user-images.githubusercontent.com/128348968/230006619-be6444e3-65cd-491d-89da-cfa979a49469.png)

```
states=dd.loc[:,["Duration","Price"]]

states=states.groupby(by=["Duration"]).sum().sort_values(by="Price")

sns.barplot(x=states.index,y="Price",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Duration")

plt.ylabel=("Price")

plt.show()
```
![image](https://user-images.githubusercontent.com/128348968/230006702-a869de24-5b32-47e5-bab7-23325817cae4.png)
# Multivariate Analysis
```
dd.corr()

data = np.random.randint(low = 1, high = 100, size = (10, 10))

print("The data to be plotted:\n")

print(data)

hm = sns.heatmap(data = data)

plt.show()
```
![image](https://user-images.githubusercontent.com/128348968/230006845-d5ba11f3-bb0c-4050-9bc0-81a53be8d736.png)
# RESULT:
Thus, Bivariate/Multivariate Analysis is performed successfully.
