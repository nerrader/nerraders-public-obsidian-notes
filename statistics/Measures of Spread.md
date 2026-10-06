There are four measures of spread: range, IQR, variance and standard deviation.
## Range

Range is the $highestValue - lowestValue$, measuring, well, the range of the dataset.

> [!EXAMPLE]
> 
> Lets say I have a dataset like {1, 5, 100, 2, -3, -6}
> 
> The range would just be 100 - (-6) which is 106.
## IQR

IQR measures the spread of the middle 50% of the data.
$IQR = Q3 - Q1$

> [!EXAMPLE]
Lets say I have a dataset like {1, 2, 4, 5, 5, 6, 7, 10}
>
Q2 would be the median of the dataset, or the middle of the dataset, which is 5, so Q2 = 5
Now the dataset is divided into half: {1, 2, 4, 5} and {5, 6, 7, 10}
>
Q1 would divide the first half into the dataset into two further groups by finding the median of the first group, which is 3, Q1 = 3.
>
Q3 would divide the second half of the dataset into two further groups, finding the median again, Q3 = 6.5
>
By using our formula for IQR, 6.5 - 3 = 3.5
meaning the IQR, or the spread of data in the middle 50% of the data would be 3.5
## Variance

Variance measures the average squared distance of values from mean.

To calculate variance, you find difference between each value and the mean, square it, then take the average of those squared differences.

> [!EXAMPLE]
Lets say I have a dataset with {1, 2, 4, 5}
>
The mean value is 3.
The difference from the value to mean is -2, -1, 1, 2 respectively.
Since you cant just use the mean formula to find the average as the negative and positive values would cancel each other out, you must square them first, so
4, 1, 1, 4
>
Then find the average of those values, which is 2.5
The variance of that particular dataset is 2.5

## Standard Deviation

Standard Deviation, also known as just SD is just the square root of the variance, and this is one of the more common measures of spread used in analysis.

The reason Standard Deviation and not variance is more common is because variance is expressed in square units. As an example, if your data was measured in meters, the variance would be in squared meters ($m^2$). To transform it back to the original unit, you square root the variance.

There are two main types of standard deviation, sample standard deviation, and population standard deviation. The formula for standard deviation changes between these two types.

**Sample Standard Deviation:

$s = \sqrt{\frac{\sum_{i=1}^{n}(x_i-\bar{x})^2}{n-1}}$

**Population Standard Deviation:

$\sigma = \sqrt{\frac{\sum_{i=1}^{N}(x_i-\mu)^2}{N}}$

The reason sample standard deviation is divided by $n-1$ and not $N$ is due to Bessel's correction.

tbh i have no clue how it works just know that if youre using a sample you have to divide by $n-1$