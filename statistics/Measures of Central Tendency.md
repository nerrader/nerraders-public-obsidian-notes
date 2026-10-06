There are several ways to find the "center" of a dataset, there is the mean, median and mode.

- The mean describes the average of the values, which is the sum divided by the number of values.
- The median is the middle value when the data is ordered from smallest to largest. If there are two values in the middle, the median is the mean of those two values
- The mode is the number that occurred the most in the dataset.

There are also two types of means: the sample mean and the population mean.

The sample mean is the average of values taken from a sample of the entire population
The population mean is the average of values taken from an entire population

Lets say I'm trying to measure the average height of students in a school of 1 000 students, it would be way too time-consuming and faster to just get a randomly selected pool of 100-200 students, then calculate the average. That is a sample mean. A population mean would mean getting the height of those 1 000 students and averaging it out.

> [!EXAMPLE] Example Dataset
> 
> Lets say I was measuring the average test scores of a student, the dataset is:
> ${50, 65, 75, 85, 85, 90}$
> 
> - The mean or average would be $\frac{50+65+75+85+85+90}{6}$ , which is 75.
> - There are two middle numbers: 75 and 85, so $\frac{75+85}{2}$, which is 80.
> - The mode is 85, as it appeared twice in the dataset.

That shows that mean, median and mode can show different values while still displaying the "center" of a dataset.

## When to use Mean vs Median?

For analysis, use mean when you want an overall average, and the values don't have any extreme outliers, all values are close together.

For example when values are just ${80, 70, 100, 60, 80, 85}$, using mean would be reasonable as there are no extreme outliers (though using median is also fine here).

Use median when the data is skewed or has many extreme outliers that could impact your analysis or skew your average.

For example, when the dataset is {${50, 10000, 70, 80, 90, 1000}$}, using the mean would not result in a very good analysis as the mean is skewed by the high outlier. This is when using the median is more reasonable.