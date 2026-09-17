# ECE-2112-PA-4
Made by: Henley Lorin M. De Guzman | 2ECEB

This repository contains the Programming Assignment #4 for the course ECE2112 "Advanced Computer Programming and Algorithms" in the A.Y. 2026 - 2027. This assignment covers three Python programming problems related to Module 4, titled *Data Wrangling and Visualization*.

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
3) `vis_fem_passed = ...` - Filters the female group and display only who passed the Average Score of 60 or higher.
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
2) `gender_mean = b.groupby(...)` - Groups the students by `Track` and calculate their mean.
3) `hometown_mean = b.groupby(...)` - Groups the students by `Track` and calculate their mean.
