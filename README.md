# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import seaborn as sns
import matplotlib.pyplot as plt
df = sns.load_dataset("tips")
df
```
<img width="560" height="504" alt="image" src="https://github.com/user-attachments/assets/94e596f4-883f-4d99-8cd5-c2034f15b191" />

```
sns.lineplot(x="total_bill", y="tip", data=df, hue="sex", linestyle="solid", legend="auto", palette="Set1")
```
<img width="723" height="573" alt="image" src="https://github.com/user-attachments/assets/49e4b57a-48d4-4086-8112-c60cf1eaaede" />

```
x = [1,2,3,4,5]
y1 = [3,5,2,6,1]
y2 = [1,6,4,3,8]
y3 = [5,2,7,1,4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel('Y Label')
```
<img width="715" height="602" alt="image" src="https://github.com/user-attachments/assets/20b565c1-056d-4aba-8080-5efc17a3313d" />

```
tips = sns.load_dataset("tips")
avg_total_bill = tips.groupby("day")["total_bill"].mean()
avg_tip = tips.groupby("day")["tip"].mean()
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index, avg_total_bill,label='Total Bill')
p2=plt.bar(avg_tip.index, avg_tip,bottom=avg_total_bill, label='Tip')
plt.xlabel("Day of the week")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Day")
plt.legend()
plt.show()
```
<img width="768" height="704" alt="image" src="https://github.com/user-attachments/assets/04503a75-804f-42d1-b7bf-e6ed86df2690" />

```
avg_total_bill = tips.groupby("time")["total_bill"].mean()
avg_tip = tips.groupby("time")["tip"].mean()
p1=plt.bar(avg_total_bill.index, avg_total_bill,label='Total Bill',width=0.4)
p2=plt.bar(avg_tip.index, avg_tip,bottom=avg_total_bill, label='Tip',width=0.4)
plt.xlabel("Time of the day")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Time of the Day")
plt.legend()
```
<img width="720" height="686" alt="image" src="https://github.com/user-attachments/assets/1b54c7d6-1e28-4611-954b-53794e7e370c" />

```
import seaborn as sns
df = sns.load_dataset("tips")
sns.barplot(x="day", y="total_bill", hue="sex",data=df,palette='Set3')
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Total Bill by Day and Gender")
```
<img width="717" height="596" alt="image" src="https://github.com/user-attachments/assets/4e017430-b907-42ea-8659-c4ae36d5ab4a" />

```
import seaborn as sns
df = sns.load_dataset("tips")
sns.scatterplot(x="total_bill", y="tip", hue="sex",data=df,palette='Set1')
plt.xlabel("Total Bill")
plt.ylabel("Tip")
plt.title("Scatter Plot of Total Bill vs Tip Amount")
```
<img width="713" height="590" alt="image" src="https://github.com/user-attachments/assets/76748d82-1880-42cf-be33-4f6205f8229e" />

```
sns.histplot(data=df,x="total_bill",hue="smoker",kde=True,palette='Set1')
plt.xlabel("Total Bill")
plt.ylabel("Frequency")
plt.title("Distribution of Total Bill by Gender")
```
<img width="716" height="597" alt="image" src="https://github.com/user-attachments/assets/050f283d-c840-4193-97d8-63f1360e5800" />

```
import seaborn as sns
import pandas as pd
df = sns.load_dataset('tips')
sns.boxplot(x='day', y='total_bill',hue='sex',data=df, palette='Set2')
```
<img width="717" height="569" alt="image" src="https://github.com/user-attachments/assets/829c5981-bd0b-41fa-bfc7-5a6170f233c7" />

```
sns.boxplot(x="day",y="total_bill",hue="smoker",data=df,linewidth=2,width=0.6,fliersize=7,flierprops={"marker":"o","markerfacecolor":"grey"},boxprops={"facecolor":"red","edgecolor":"black"},whiskerprops={"color":"darkblue","linestyle":"--","linewidth":"-","linewidth":2},palette="Set1")
```
<img width="725" height="567" alt="image" src="https://github.com/user-attachments/assets/740d0458-4296-413f-8f1a-40a6d4c99223" />

```
sns.violinplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,palette="Set1",inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
<img width="709" height="599" alt="image" src="https://github.com/user-attachments/assets/84b3330d-956b-474d-95d0-eb146a6753ed" />

```
import seaborn as sns
sns.set(style="whitegrid")
tip = sns.load_dataset("tips")
sns.violinplot(x="day", y="tip", data=tip, palette="Set2")
```
<img width="743" height="699" alt="image" src="https://github.com/user-attachments/assets/0199fc59-3b79-442e-a9a1-5c4171b93d25" />

```
import seaborn as sns
sns.set(style="whitegrid")
tip = sns.load_dataset("tips")
sns.violinplot(x=tip["total_bill"],palette="Set1")
```
<img width="760" height="698" alt="image" src="https://github.com/user-attachments/assets/6d67f04f-f801-4baf-8ea4-41257b247cf5" />

```
import seaborn as sns
sns.set(style="whitegrid")
tip = sns.load_dataset("tips")
sns.violinplot(x="tip",y="day",data=tip,palette="rainbow")
```
<img width="756" height="701" alt="image" src="https://github.com/user-attachments/assets/d1cefcc9-bcfd-4d80-acea-a95701af8df5" />

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple="layer",linewidth=3,palette="Set2",alpha=0.8)
```
<img width="762" height="583" alt="image" src="https://github.com/user-attachments/assets/9bc2127c-b52f-4198-95ac-2ef18dd8d126" />

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple="stack",linewidth=3,palette="Set3",alpha=0.8)
```
<img width="753" height="582" alt="image" src="https://github.com/user-attachments/assets/ffe8a935-9a32-400f-a1dc-93afb9a1ea7d" />

```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple="fill",linewidth=3,palette="Set1",alpha=0.8)
```
<img width="742" height="590" alt="image" src="https://github.com/user-attachments/assets/3a0f55e1-6306-4a12-98df-0b3154517487" />

```
import seaborn as sns
tip = sns.load_dataset("tips")
num = tips.select_dtypes(include=['float64','int64']).columns
corr = tips[num].corr()
sns.heatmap(corr,annot=True,cmap='YlGnBu')
```
<img width="676" height="561" alt="image" src="https://github.com/user-attachments/assets/f56cf463-eddf-4df6-9087-9ba038f77285" />

```
sns.heatmap(corr,cmap='YlGnBu')
```
<img width="675" height="558" alt="image" src="https://github.com/user-attachments/assets/8198e0cf-b8d7-4d3a-9ad6-ba235f80c4c3" />

# Result:
 Thus, the Data Visualization using seaborn python library for the given data executed successfully.
