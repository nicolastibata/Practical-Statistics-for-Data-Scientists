# Summary - Chapter 1: Exploratory Data Analysis 

- Exploratory data analysis was established by John Tukey and his classic book in 1977.

&nbsp;
## Elements of Structured Data
> The major challenge of data science is to harness torrent of raw data into actionable information.

- There are two basic types of structured data:

| Data Types | Description |
| :--- | :--- |
| **Numeric** | Data that are expressed on a **numeric scale**. |
| &nbsp;&nbsp;Continuous | Data that can take on any value in an interval (float, numeric, interval...). |
| &nbsp;&nbsp;Discrete | Data can take on only integer values, such as counts (integer, count). |
| **Categorical** | Data that can take on only specific set of values representing a set of possible categories (enums, enumerated, factors, nominal). |
| &nbsp;&nbsp;Binary | A special case of categorical data with just two categories of values (0/1 ; true/false) (dichotomous, logical, boolean, indicator...).
| &nbsp;&nbsp;Ordinal | Categorical data that has an explicit ordering (ordered factor).

Identification of data as categorical offer some advantages:
- Knowing that data is categorical can act as a signal telling software how statistical procedures, such as producing a chart or fitting a model, should behave.
- Storage and indexing can be optimized (as in relational database).

Data typing in software acts as a signal to the software on how to process the data.

&nbsp;
## Rectangular Data
> Rectangular Data is the general term for a two-dimensional matrix with rows indicating records (cases) and columns indicating features (variables); 'data frame' is the specific format in R and Python.

The data doesn't always start in a rectangular form (*i.e text or relational databases*).

| Key Terms | Description |
| ---- | ---- |
| **Data Frame** &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; | Rectangular data (like spreadsheet) is the basic data structure for statistical and machine learning models. |
| **Feature** | A column within a table is commonly referred to as a feature (attribute, input, predictor, variable). |
| **Outcome** | The features are some times used to predict the *outcome* in an experiment or a study (dependent variable, response, target, output). |
| **Records** | A row within a table is commonly referred to as a record (case, example, observation, sample).

> **Terminology Differences**: For a statistician, predictor variables are used in a model to predict a **response** or dependent variable. For a data scientist, features are used to predict a **target**. One synonym is particularly confusing: computer scientist will use the term **sample** for a single row; a **sample** to a statistician means a collection of rows.

&nbsp;
### Nonrectangular Data Structures
- **Time Series Data**: Records succesive measurements of the *same variable*.
- **Spatial Data Structures**: Are used in mapping and location analytics.
- **Graph (or network) Data Structures**: Are used to represent physical, social and abstract relationships.

> In computer science and information technology, the term **graph** typically refers to a depiction of the connections among entities. In statistics, **graph** is used to refer to a variety of plots and visualizations (just visualizations, not the data structure).

&nbsp;
## Estimates of Location
| **Key Terms for Estimates of Location** | Description |
| :---- | :---- |
| **Mean** | The sum of all values divided by the number of values (average). |
| **Weighted Mean** | The sum of all values times a weight divided by the sum of the weights (weighted average). |
| **Median** | The value such that one-half of the data lies above and below (50th Percentile). |
| **Percentile** | The value such that P percent of the data lies below (quantile). |
| **Weighted Median** | The value such that one-half of the sum of the weights lies above and below the sorted data. |
| **Trimmed Mean** | The average of all values after dropping a fixed number of extreme values (truncated mean). |
| **Robust** | Not sensitive to extreme values (resistant). |
| **Outlier** | A data value that is very different from most of the data (extreme value). |

> **Weighted Mean** has two main motivations: (1) Some values are intrinsically more variable than others, and highly variable observations are given lower weight. (2) The data collected does not equally represent the different groups that we are interested in measuring. To correct that, we can give a higher weight to the values from the groups that were underrrepresented.

> The basic metric for location is the mean, but it can be sensitive to extreme values (outlier).
Other metrics (median, trimmed mean) are less sensitive to outliers and unusual distributions and hence are more robust.

&nbsp;
## Estimates of Variability

| Key Terms for Variability Metrics | Description |
| :----- | :------ |
| **Deviations** | The difference between the observed values and the estimate of location (errors, residuals). |
| **Variance** | The sum of squared deviations from the mean divided by n - 1 where n is the number of data values (mean-squared-error). |
| **Standard Deviation** | The square root of the variance. |
| **Mean Absolute Deviation** | The mean of the absolute values of the deviations from the mean (l1-norm, Manhattan norm). |
| **Median Absolute Deviation from the Median** | The median of the absolute values of the deviations from the median. |
| **Range** | The difference between the largest and the smallest value in the data set. |
| **Order Statistics** | Metrics based on the data values sorted from the smallest to biggest (ranks). |
| **Percentile** | The value such that P percent of the values take on this values or less and (100 - P) percent take on this value or more. |
| **Interquartile Range** | The difference between the 75th percentile and the 25th percentile (IQR). |

> Is peculiar that the standard deviation is preferred in statistics over the mean absolute deviation. This is because working with squared values is much more convenient than absolute values, especially for statistical models.

> Neither the Variance, Standard Deviation, nor the Mean Absolute Deviation is robust to outliers and extreme values. The first two are specially sensitive to outliers since they are based on the squared deviations. 
A robust estumate of variability is the **median absolute deviation** (MAD) since is not influenced by extreme values.

&nbsp;
## Exploring the Data Distribution

| Key Terms for Exploring the Distribution &nbsp; &nbsp;&nbsp; | Description |
| :---- | :---- |
| **Boxplot** | A plot introduced by Tukey as a quick way to visualize the distribution of data (box and whiskers plot). |
| **Frequency Table** | A tally of the count of numeric data values that fall into a set of intervals (bins). |
| **Histogram** | A plot of the frequency table with the bins on the x-axis and the count on the y-axis. While visually similar, bar charts should not be confused with histograms. |
| **Density Plot** | A smoothed version of the histogram, often based on a *kernel density estimate*. |

&nbsp;
### Frequency Tables and Histograms
> Percentiles show variability in the data.

> Both frequency tables and percentiles summarize the data by creating bins. In general, quartiles and deciles will have the same count in each bin (equal-count bins), but the bin sizes will be different. The frequency table, by contrast, will have different counts in the bins (equal-size bins), and the bin sizes will be the same.

> **Location** and **Variability** are referred to as the **first** and **second** moments of a distribution. The third and fourth moments are called skewness and kurtosis.
Skewnees: Refers to whether the data is skewed to larger or smaller values.
Kurtosis: Indicates the propensity of the data to have extreme values.
Skewness and Kurtosis are not measure with metrics, these are discovered through visual displays (as Boxplots and Histograms).

&nbsp;
### Density Plots and Estimates
- Related to the histogram is a density plot, which shows the distribution of data values as a continuous line.
- A density plot corresponds to plotting the histogram as a proportion rather than counts, which the total area under the density curve = 1. 

&nbsp;
## Exploring Binary and Categorical Data

| Key Terms for Exploring Categorical Data | Description |
| :------ | :----- |
| **Mode** | The most commonly ocurring category or value in a data set. |
| **Expected Value** | When the categories can be associated with a numeric value, this gives an average value based on a category's probability of occurrence. |
| **Bar charts** | The frequency or proportion for each category plotted as bars. |
| **Pie charts** | The frequency or proportion for each category plotted as wedges in a pie. |

> Bar charts, seen often in the popular press, are a common visual tool for displaying a single categorical variable. Categories are listed on the x-axis, and frequencies or proportions on the y-axis.

> Categories might represent distinct things (apples or oranges, male or female), **levels of a factor** variable (low, medium, high), or **numeric data that has been binned**. 

> Expected value is the sum of values times their probability of ocurrence, often used to sum up factor variables levels.

&nbsp;
### Correlation
| Key Terms for Correlation &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Description |
| :---- | :----- | 
| **Correlation Coefficient** | A metric that measures the extent to which numeric variables are associated with one another (ranges from - 1 to + 1). |
| **Correlation Matrix** | A table where the variables are shown on both rows and columns, and the cell values are the crrelations between the variables. |
| **Scatterplot** | A plot in which the x-axis is the value of one variable, and the y-axis the value of another. |

> The correlation coefficient gives an estimate of the correlation between two variables that always lies on the same scale.
We multiply deviations from the mean for variable 1 times those for variable 2, and divide by the product of the standard deviations.

> **Positively Correlated**: If high values of X go with high values of Y (or viceversa).
**Negatively Correlated**: If high values of X go with **low** values of Y (or viceversa)

> **Variables can have an association that is not linear, in which case the correlation coefficient may not be a useful metric.**

&nbsp;
## Exploring Two or More Variables 
> Estimators like mean and variance look at variables one at a time ( univariate analysis ). Correlation analysis is an important method that compares two variables ( bivariate analysis ). In this section will se the **multivariate analysis**.

| Key Terms for Exploring Two or More Variables | Description |
| :----- | :------ |
| **Contingency Table** | A tally of counts between two or more categorical variables. |
| **Hexagonal Binning** | A plot of two numeric variables with the records binned into hexagons. |
| **Contour Plot** | A plot showing the density of two numeric variables like a topographical map. &nbsp;&nbsp;&nbsp;&nbsp; |
| **Violin Plot** | Similar to a boxplot but showing the density estimate. |

> For data sets with hundreds of thousands or millions of records, a scatterplot will be too dense, so we need a different way to visualize the relationship ( Hexagonal Binning and Contours ).

> The contours are essentially a topographical map to two variables; each contour band represents a specific density of points, increasing as one nears a peak.

&nbsp;
### Two Categorical Values
-  A useful way to summarize two categorical variables is a **contingency table**, which is a a table of counts by category.

&nbsp;
### Categorical and Numeric Data

- Boxplots are a simple way to visually compare the distributions of a numeric variable agrouped according to a categorical variable.
- A violin plot, introduced by Hintze-Nelson, is an enhancement to the boxplot and plots the density estimate with the density on the y-axis. The density is mirrored and flipped over, and the resulting shape is filled in, creating an image resembling a violin.
    - The advantage of a violin plot is that it can show nuances in the distribution that aren't perceptible in a boxplot. On the other hand, **the boxplot more clearly shows the outliers in the data**.

&nbsp;
### Visualizing Multiple Variables 
> Conditioning: The concep of conditioning variables in a graphics system was pioneered with Trellis Graphics, developed by Rick Becker, Bill Cleveland, and others. This idea has propagated to various modern graphics systems, such as lattice and ggplot2 in R, and seborn and bokeh modules in python, also Tableau and Spotfire.
