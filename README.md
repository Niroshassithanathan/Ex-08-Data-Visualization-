# Ex-07-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
```
NAME:NIROSHA.S
REGISTER NUMBER:21222230097
## DATA:
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import seaborn as sbn
df=pd.read_csv("/content/Superstore.csv",encoding='windows-1252')
df.head()

# DATA CLEANING
df.info()

df.isnull().sum()

1.Which Segment has Highest sales?
sbn.barplot(x=df['Segment'],y=df['Sales'])
plt.title("Highest Sales of the segment")

2.Which City has Highest profit?
sbn.barplot(x=df['City'],y=df['Profit'])
plt.title("Highest Profit of cities")

City=df.loc[:,["City","Profit"]]
df.head(5)
City=City.groupby(by=["City"]).sum().sort_values(by="Profit")
plt.figure(figsize=(10,10))
sbn.barplot(x=City.index,y="Profit",data=City)
plt.xticks(rotation = 90)
plt.xlabel=("City")
plt.ylabel=("Profit")
plt.show()

3.Which ship mode is profitable?
sbn.barplot(x=df['Ship Mode'],y=df['Profit'])
plt.title("Profitable Ship Mode")

4.Sales of the product based on region.
sbn.barplot(x=df['Sales'], y=df['Region'])
plt.title("Sales of Product based on Region")

5.Find the relation between sales and profit.
sbn.lineplot(x=df['Sales'], y=df['Profit'])
plt.title("Relation between Sales and Profit")

6.Find the relation between sales and profit based on the following category. i) Segment ii)City iii)States iv)Segment and Ship Mode v)Segment, Ship mode and Region

i) Segment
grouped_data = df.groupby('Segment')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
ax.legend()
plt.show()

ii) City
grouped_data = df.groupby('City')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('City')
ax.set_ylabel('Value')
ax.legend()
plt.show()

iii) States
grouped_data = df.groupby('State')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('State')
ax.set_ylabel('Value')
ax.legend()
plt.show()

iv)Segment and Ship Mode
grouped_data = df.groupby(['Segment', 'Ship Mode'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index='Segment', columns='Ship Mode', values=['Sales', 'Profit'])
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
pivot_data.plot(kind='bar', ax=ax)
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
plt.legend(title='Ship Mode')
plt.show()

v)Segment, Ship mode and Region
grouped_data = df.groupby(['Segment', 'Ship Mode','Region'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index=['Segment', 'Ship Mode'], columns='Region', values=['Sales', 'Profit'])
sns.set_style("whitegrid")
sns.set_palette("Set1")
pivot_data.plot(kind='bar', stacked=True, figsize=(10, 5))
plt.legend(title='Region')
plt.show()
```
# OUPUT

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/91cfd5eb-765c-4ff1-b3db-63193ec14703)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/dbb0d6cf-2cdd-49f6-971d-21d523a1a96f)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/311eca0e-c19d-432a-9348-e8cbd307df99)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/a8f77e91-de8d-4a43-99d6-0b676d463b99)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/0f4c521f-e150-4c39-9851-33b2ce67e08d)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/7deaecc6-0b5c-42df-8863-debcbdab6435)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/329d7f88-4da6-49f5-8be6-b4957d72aac7)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/0605ebee-213f-48b0-9078-e1eddb5113fe)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/ba237962-284f-4f01-acf8-b9ed67037da7)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/60bed3fc-f25a-4db2-a015-ad74239bb7df)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/b98b0f9c-3e73-4969-a891-c20f3ed92d8e)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/d06f7bb6-d566-4c28-baaa-d26618401e84)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/506a243f-6add-49b3-8058-4aab598d6591)

![image](https://github.com/Niroshassithanathan/Ex-08-Data-Visualization-/assets/121418437/22e1e557-e8ae-412a-8dfa-60786a6c0ff6)


## BRESULT:

Hence the data visualization method for the given dataset applied successfully.
