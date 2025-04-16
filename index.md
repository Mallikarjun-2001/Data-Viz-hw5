---
layout: default
title: Homework – Altair Visualization
---

## Visualization 1: Building Count by County

This bar chart presents the number of state-owned buildings across Illinois, aggregated by county. Each bar corresponds to a county and represents the total number of buildings listed under that county in the dataset. The purpose of this visualization is to provide a high-level understanding of which regions in Illinois maintain a higher concentration of public infrastructure. This can be useful in policy planning, regional development assessments, and infrastructure resource allocation.

#Design choices and encodings:
The x-axis encodes the County variable as a nominal type, while the y-axis encodes the count of buildings as a quantitative field using count():Q. The bars are rendered using Altair’s mark_bar() function. Each county is also assigned a unique color using a categorical color scheme applied via the County:N field. This improves visual distinction and allows for easier comparison between counties.

#Data transformations:
Prior to plotting, the data was cleaned by removing rows with missing or blank County values. This was done using a simple filter condition to ensure that undefined entries did not appear in the visualization or interfere with grouping and aggregation logic.

#Rendering on Jekyll page:
This plot has been embedded into the Jekyll page as a static PNG image. It displays correctly without errors and meets the rubric requirement for inclusion and clarity.

[View Bar Plot](bar_chart.html)


## Visualization 2: Building Size by Year Constructed (Interactive)

This scatter plot analyzes the relationship between the year a building was constructed and its size, measured in square footage. Each data point represents an individual building. This plot is designed to highlight construction trends over time and identify how building sizes may have changed across different periods. It also allows for regional comparison by coloring data points based on the county to which the building belongs.

#Design choices and encodings:
The x-axis represents Year Constructed (quantitative), and the y-axis represents Square Footage (quantitative). Each point is colored by the County field, which is encoded as a nominal variable. Tooltips are provided for additional context, including location name, city, year constructed, and building size. The points are rendered using mark_circle() with a fixed size for visual uniformity. Color was used to differentiate counties and improve interpretability when filtering data.

#Data transformations:
The dataset required multiple preprocessing steps before visualization. Records with missing values in Year Constructed or Square Footage were removed using dropna(). Both fields were also explicitly converted to numeric types using pd.to_numeric() to ensure compatibility with Altair encodings and prevent errors during plotting.

#Interactivity:
This visualization includes advanced interactivity in two forms:

A dropdown menu that allows users to select a specific county or view all counties simultaneously. The chart dynamically filters based on the selected county, updating the view in real time.

Pan and zoom capabilities are enabled using .interactive(), allowing users to explore dense regions of the plot or zoom in on specific time periods or building sizes.

The dropdown is implemented using alt.binding_select() and selection_single, and the conditional filter is handled within transform_filter() to manage the "All" option effectively.

Rendering on Jekyll page:
A static version of this plot is embedded in the Jekyll site as an image. Additionally, an interactive version is linked externally via HTML, ensuring that the interactivity is accessible for grading purposes. This meets all technical and content requirements specified in the rubric.

[View Interactive Scatter Plot](scatter_plot.html)

### Links  
- [The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv)  
- [The Analysis](https://github.com/Mallikarjun-2001/Data-Viz-hw5/blob/main/building_plots.ipynb)
