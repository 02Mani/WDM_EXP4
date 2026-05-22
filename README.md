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

### Program:
```python
import pandas as pd

# Read the CSV file into a DataFrame
data = pd.read_csv('clustervisitor.csv')

# Define age groups using a dictionary with Boolean conditions
age_groups = {
    '18-24': (data['Age'] >= 18) & (data['Age'] <= 24),
    '25-34': (data['Age'] >= 25) & (data['Age'] <= 34),
    '35-44': (data['Age'] >= 35) & (data['Age'] <= 44),
    '45-54': (data['Age'] >= 45) & (data['Age'] <= 54),
    '55-64': (data['Age'] >= 55) & (data['Age'] <= 64),
    '65+': (data['Age'] >= 65)
}

# Segment visitors by iterating through the age groups and filter visitors into respective groups
segmented_visitors = {
    group: data[condition]
    for group, condition in age_groups.items()
}

# Count the number of visitors in each age group
visitor_counts = [
    len(segmented_visitors[group])
    for group in age_groups
]

# Define age group labels
age_group_labels = list(age_groups.keys())

```
### Output:
<img width="410" height="599" alt="image" src="https://github.com/user-attachments/assets/8fbba8ce-00ad-47c4-a169-8c4b1315bf48" />


### Visualization:
```python
#import matplotlib.pyplot as plt

# Plot a bar chart for visitor distribution across age groups
plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
<img width="798" height="595" alt="image" src="https://github.com/user-attachments/assets/6395478b-e553-4fd9-804e-e2a16fa2a286" />

<img width="729" height="580" alt="image" src="https://github.com/user-attachments/assets/422e2226-082f-4f9c-a7be-bb505a8ac1b4" />

### Result:
Thus, visitor segmentation based on age groups was successfully done using Python.
