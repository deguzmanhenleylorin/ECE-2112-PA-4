# ECE-2112-PA-4
Made by: Henley Lorin M. De Guzman | 2ECEB

This repository contains the Programming Assignment #4 for the course ECE2112 "Advanced Computer Programming and Algorithms" in the A.Y. 2026 - 2027. This assignment covers three Python programming problems related to Module 4, titled *Data Wrangling and Visualization*.

**IMPORTING LIBRARIES AND DATASETS**

The following functions and methods were used and executed in this:

1) `import pandas as pd` - To import Pandas library
2) `import matplotlib.pyplot as plt` - To import the Pyplot module from Matplotlib
3) `pd.read_excel` - To read the xlsx file and loads it into Python Dataframe

**A. VISAYAS COMMUNICATION DATAFRAME**

The following functions and methods were used and executed in this problem:

1) `vis_comm_mask = ...` - Use to create a filter to check which students are both from `Visayas` and `Communication`.
2) `VisComm = b.loc[...]` - Use to grab the students from Visayas and diplaying their `Name, Gender, Math, Electronics, and Average`.
```python
vis_comm_mask = (b["Hometown"] == "Visayas") & (b["Track"] == "Communication")

VisComm = b.loc[vis_comm_mask, ["Name", "Gender", "Math", "Electronics", "Average"]]
VisComm
```

**B. VISAYAS FEMALE DATAFRAME**

The following functions and methods were used and executed in this problem:

1) `vis_female_mask = ...` - Use to create a filter to check which students are from `Visayas` and are `Female`.
2) `VisFemale = b.loc[...]` - Use to grab the female students and display their `Name, Track, GEAS, Electronics, and Average`
3) `vis_fem_passed = ...` - Filters the female group and display only who passed the `Average Score` of 60 or higher.
```python
vis_female_mask = (b["Hometown"] == "Visayas") & (b["Gender"] == "Female")

VisFemale = b.loc[vis_female_mask, ["Name", "Track", "GEAS", "Electronics", "Average"]]
VisFemale

vis_fem_passed = VisFemale.loc[VisFemale["Average"] >= 60]
vis_fem_passed
```

**C. CATEGORY-AVERAGE VISUALIZATION**

The following functions and methods were used and executed in this problem:

1) `track_mean = b.groupby(...)` - Groups the students by `Track` and calculate their mean.
2) `gender_mean = b.groupby(...)` - Groups the students by `Gender` and calculate their mean.
3) `hometown_mean = b.groupby(...)` - Groups the students by `Hometown` and calculate their mean.
4) `fig, axes = plt.subplots(...)` - Set up a side-by-side plot layout with 1 row and 3 bar charts.
5) `axes[#].(...)` - Plots calculated mean into a bar chart, and adds the title/labels.
6) `plt.tight_layout` - Fixes the visual arrangement and spacings
7) `plt.show` - Displays the figure
```python
fig, axes = plt.subplots(1, 3, figsize=(15, 5), sharey=True)

axes[0].bar(track_mean.index, track_mean.values, color="red", edgecolor="black")
axes[0].set_title("Mean Average by Track")
axes[0].set_xlabel("Track")
axes[0].set_ylabel("Mean Average")
axes[0].tick_params(axis="x", rotation=45)

axes[1].bar(gender_mean.index, gender_mean.values, color="orange", edgecolor="black")
axes[1].set_title("Mean Average by Gender")
axes[1].set_xlabel("Gender")
axes[1].tick_params(axis="x", rotation=0)

axes[2].bar(hometown_mean.index, hometown_mean.values, color="yellow",edgecolor="black")

axes[2].set_title("Mean Average by Hometown")
axes[2].set_xlabel("Hometown")
axes[2].tick_params(axis="x", rotation=45)

plt.tight_layout()
plt.show()
```

Thank you for reading!

Programming Assignment #4: https://github.com/deguzmanhenleylorin/ECE-2112-PA-4/blob/main/Programming%20Assignment%20%234.ipynb

**READ ME FILE HISTORY: **

September 17, 2026 - Initial and Finalized README output uploaded.
