### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 20-11-2026
### NAME: KOMALAVARSHINI.S
### REG No.: 212224230133
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
```

import pandas as pd
import matplotlib.pyplot as plt

# Visitor segmentation based on characteristics

# Step 1: Read the CSV file
df = pd.read_csv(r"C:\Users\admin\Downloads\clustervisitor.csv")

print("Complete Dataset")
print(df)

# Step 2: Define Age Groups
age_groups = {
    "Young": (df["Age"] >= 18) & (df["Age"] <= 30),
    "Adult": (df["Age"] >= 31) & (df["Age"] <= 45),
    "Senior": (df["Age"] > 45)
}

# Step 3: Segment Visitors
print("\nVisitor Segmentation\n")

for group, condition in age_groups.items():
    print(group, "Visitors")
    print(df[condition])
    print("-" * 40)

# Step 4: Create a list to store visitor counts
visitor_counts = []

# Count visitors in each age group
for group, condition in age_groups.items():
    visitor_counts.append(df[condition].shape[0])

# Define age group labels
age_group_labels = list(age_groups.keys())

# Plot bar chart
plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')

plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()

```
### Output:

<img width="1492" height="766" alt="image" src="https://github.com/user-attachments/assets/49204953-0ada-427b-97bd-df81bcdb464d" />


<img width="1502" height="775" alt="image" src="https://github.com/user-attachments/assets/2b434c27-923a-44e8-93d4-e294c4c20442" />


<img width="1471" height="693" alt="image" src="https://github.com/user-attachments/assets/74685b74-c97c-4854-9e7f-daecf7d93aa2" />



### Result:
Thus, Cluster and Visitor Segmentation was successfully implemented using Python. The visitors were categorized into three age groups: Young, Adult, and Senior. The distribution of visitors was visualized successfully using a bar chart.
