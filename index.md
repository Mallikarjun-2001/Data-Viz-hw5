---
layout: default
title: Homework – Altair Visualization
---

## Visualization 1: Building Count by County

This bar chart illustrates the distribution of state-owned buildings across Illinois counties. Each bar represents the count of buildings in a particular county. To clean the data, I removed any entries with missing or blank county values. I used a nominal encoding for county names on the x-axis, and a quantitative encoding for the count on the y-axis. A unique color was assigned to each county for visual distinction. The plot was designed to give a clear comparative view of how building counts vary across regions.

## Visualization 2: Building Size by Year Constructed (Interactive)

This scatter plot visualizes the relationship between the year a building was constructed and its size (in square footage). I filtered out rows with missing or non-numeric values for both axes and used Altair’s `.interactive()` to allow zooming and panning. The color represents the county, and tooltips were added for richer context on hover. The interactive design helps users explore temporal construction trends and identify unusually large or small buildings more intuitively.

### Links  
- [The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv)  
- [The Analysis](https://github.com/Mallikarjun-2001/Data-Viz-hw5/blob/main/building_plots.ipynb)
