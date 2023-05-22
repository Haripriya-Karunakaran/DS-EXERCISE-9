## DS-EXERCISE-9       

## DATA VISUALIZATION

### Aim:

To Perform Data Visualization on a complex dataset and save the data to a file.

### Explanation:

Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide

an accessible way to see and understand trends, outliers, and patterns in data.

### Algorithm:

Step 1 : Read the given Data.

step 2: Clean the Data Set using Data Cleaning Process.

step 3: Apply Feature generation and selection techniques to all the features of the data set.

Step 4: Apply data visualization techniques to identify the patterns of the data.

### Code:

import seaborn as sns

import pandas as pd

import matplotlib.pyplot as plt

df = sns.load_dataset("tips")

print(df)

df.isnull().sum()

plt.figure(figsize=(8,8))

plt.title("Data with Outliers")

df.boxplot()

plt.show()

plt.figure(figsize=(8,8))

cols = ['size','tip','total_bill']

Q1 = df[cols].quantile(0.25)

Q3 = df[cols].quantile(0.75)

IQR = Q3 - Q1

df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]

plt.title("Dataset after removing outliers")

df.boxplot()

plt.show()

sns.barplot(x=df['day'], y=df['total_bill'], hue=df['day'])

plt.legend(loc="center")

plt.title("Highest Total Bill Amount by day of the week")

plt.show()

sns.boxplot(x=df['smoker'], y=df['tip'], hue=df['smoker'])

plt.title("Average Tip Amount given by smokers and non-smokers")

df["tip_percent"] = df["tip"] / df["total_bill"]

sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)

plt.title("Tip Percentage by Dining Party Size")

sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])

plt.title("Tips based on gender")

sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])

plt.legend(loc="best")

plt.title("Total bill amount by day of the week")

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])

plt.title("Average Total Bill Amount by Dining Party Size")

plt.show()

sns.boxplot(x="day", y="tip", data=df)

plt.title("Tip Amount by Day of Week")

plt.show()

sns.violinplot(x="time", y="tip", data=df)

plt.title("Tip Amount by Time of Day")

plt.show()

sns.scatterplot(x="total_bill", y="tip", data=df)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()

### Output:

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/d7d83540-7ef3-4e25-81af-5bd0ae03d31a)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/cce5895c-f308-41aa-a5db-fed352e804d8)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/2e53d3bc-e498-41ca-874b-300b6be38c15)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/192d7d2a-ad08-4a17-813c-9ba8d47a2916)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/b194b4c5-eff2-4dc6-ba8b-82b037dcc94d)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/b979f05a-9648-4e12-8309-76e35c6a21d7)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/266724db-6a3c-46ab-afe2-3612f371d3c9)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/dfb9d998-c6ff-4f95-b1fe-f4cca05d133b)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/23fa4bca-9ed9-4f3e-bb26-b831e68b16cf)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/904ed527-7e49-4a5a-a544-702d447022b0)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/57603a77-8cf2-414f-bb4b-e62923a83250)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/49ce9342-363d-430f-b38a-780de129e0b8)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/646d4638-2f6b-464e-982a-492bf809d09f)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-9/assets/126390051/f06e3876-e134-4c4b-9536-e045453a8b31)

### Result:

Thus, the Feature Visualization for the given datasets had been executed 
successfully
