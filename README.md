### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 22-05-2026
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Name: Manikandan M
### Reg No: 212224040183
### Program:
```python
import pandas as pd
df= pd.read_csv('/content/drive/MyDrive/Web Data MIning/clustervisitor.csv')
print(df)
```
### Output:

<img width="568" height="689" alt="image" src="https://github.com/user-attachments/assets/fc8615db-a6e3-4d18-a345-e4d0646602bf" />

### Visualization:
```python
cluster={"Young":(df['Age']<=30),"Middle":((df['Age']>30) & (df['Age']<=50)),"Old":(df['Age']>50)}
count=[]
for group,condition in cluster.items():
  visitors=df[condition]
  count.append(len(visitors))
  print(f"The visitors on {group} are :")
  print(visitors)
  print("count=",len(visitors))

import matplotlib.pyplot as plt
plt.figure(figsize=(8,6))
plt.bar(['Young','Middle','Old'],count,color="skyblue")
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title("Visitor Distribution Across Age Groups")
plt.show()
```
### Output:
<img width="741" height="578" alt="image" src="https://github.com/user-attachments/assets/3c4db9a6-8db2-46c2-b185-9a475514b79b" />


### Result:
Thus, visitor segmentation based on age groups was successfully done using Python.


