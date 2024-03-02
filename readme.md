# Assignment 2
## Name: Shreya Ekande
## Date: 03/03/2024


## Programming language: Python version 3.11.5


## Dependencies: Pandas, Seaborn, Matplotlib
## Input: DecayTimecourse.txt
## Output: List of genes and their half lives, bottom_genes.txt, first10_genes.txt, top_10_GO_output, top_10_gprofiler, bottom_10_gprofiler, bottom_10_output

# Script Description:

This Python script performs the following tasks using data from DecayTimecourse.txt :

1. **Reading Data**: The code reads from DecayTimecourse.txt and converts it into csv file. I have split the data into three separate dataframes for each replicate. 

2. **Data Cleaning**: I have cleaned the data by dropping the genes where the value is NA at the 5 minutes, i.e. first time point. For other NA values, I have interpolated the values. Interpolation calculates the missing value by considering the linear trend between the previous and next non-missing values. It's important to note that interpolate() only works for ordered data, such as time series data or data with an inherent order.

3. **Data Preprocessing**: We have the genes in rows and timepoints in columns. That would be tough for further processing. So I transosed the matrices so that the rows would have timepoints and columns would have genes. 

3. **Calculating half life**: I used Linear regression to find the line that would be fit the expression levels. After finding the line, I got the slope of the line. Using this slope, I calculated the half lives of the genes. By this logic, I found out the half lives of the gene data from all three time courses. Then I calculated the average of the three time courses. 


