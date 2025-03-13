# Walmart-Sales-Data-Analysis report
The Walmart dataset contains weekly sales data for 45 Walmart stores, along with other potentially relevant factors such as temperature, fuel price, CPI (Consumer Price Index), and unemployment rate. It also includes a 'Holiday_Flag' indicating whether a given week was a holiday week. The dataset is used to analyze sales trends and the impact of various factors on weekly sales performance.


1. Reading the Dataset

We begin by importing the necessary libraries and loading the Walmart dataset using pd.read_csv():

2. Exploring Data Structure

df_walmart.info(): This function provides an overview of the dataset's structure, including column names, data types, and the presence of missing values.

df_walmart.head(): Displays the first few rows of the dataset to get a glimpse of the data.

df_walmart.describe(): Generates descriptive statistics for numerical columns, including measures of central tendency and dispersion.

df_walmart.columns: Lists all column names in the dataset.


3. Handling Missing Values

Missing values were identified in the dataset. To avoid errors during analysis, missing values in numerical columns were imputed using the median, while missing values in categorical columns were imputed using the mode.

4. Handling Duplicates

The dataset was checked for duplicate rows using df_walmart.duplicated(keep=False). If duplicates were found, they would be printed for further inspection and potentially removed. In this case, duplicates were removed using df_walmart.drop_duplicates(inplace=True).

5. Converting 'Date' Column

The 'Date' column was initially in string format. It was converted into a proper datetime format using pd.to_datetime():

6. Outlier Detection & Removal

Outliers in numerical features ('Weekly_Sales', 'Temperature', 'Fuel_Price', 'CPI', 'Unemployment') were identified and removed using the Interquartile Range (IQR) method. This involved calculating the IQR, defining upper and lower bounds, and filtering the data to remove values outside these bounds.

7. Data Visualization

Various visualizations were created to explore the data:

Histograms: Used to visualize the distribution of numerical features, such as 'Weekly_Sales', 'Temperature', 'Fuel_Price', 'CPI', and 'Unemployment'.

Box Plots: Used to compare the distribution of 'Weekly_Sales' across different categories of 'Holiday_Flag' and 'Store', revealing potential differences and variations.

Scatter Plots: Used to visualize the relationships between 'Weekly_Sales' and other numerical features, identifying potential trends and patterns.

Correlation Heatmap: Used to visualize the correlation matrix of numerical features, highlighting strong and weak correlations.

Violin Plots: Used to visualize the distribution of 'Weekly_Sales' across different stores, highlighting variations in store performance.

Pair Plots: Used to visualize the relationships between multiple numerical features simultaneously.

8. Finding Mode for All Columns

The mode (most frequently occurring value) was computed for each column using df_walmart.mode(). This helps understand dominant trends in both categorical and numerical data.

9. Analyzing Relationships and Patterns

The analysis focused on understanding the relationships between 'Weekly_Sales' and other variables, including:

Holiday_Flag: The impact of holidays on sales was explored using box plots and grouped comparisons.

Store: Variations in sales performance across different stores were analyzed using violin plots and grouped comparisons.

Numerical Features: The relationships between 'Weekly_Sales' and numerical features like temperature, fuel price, CPI, and unemployment were investigated using scatter plots and correlation analysis.

10. Conclusion

This analysis has provided a comprehensive understanding of the Walmart dataset, revealing key insights into the factors influencing weekly sales performance. The findings highlight the importance of holidays, store-specific characteristics, and external factors in driving sales variations. Further analysis and modeling could be conducted to develop predictive models and optimize sales strategies.
