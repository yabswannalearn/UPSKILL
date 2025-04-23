![[Pasted image 20250423090217.png]]
mean
![[Pasted image 20250423090251.png]]median = add 2 in the center and divide by 2
mode - pinaka marami

![[Pasted image 20250423090845.png]]
range

![[Pasted image 20250423090921.png]]
variance
![[Pasted image 20250423105009.png]]
probability

![[Pasted image 20250423105934.png]]
conditional probability


---
# Statistical Measures Guide

## Measures of Center

### Mean (Average)

Add up all numbers and divide by how many there are. It's the "balance point" of your data.

- **Example**: Mean of [5, 10, 15] = (5+10+15)/3 = 10

### Median

The middle value when all numbers are arranged in order. If there's an even count, take the average of the two middle values.

- **Example**: Median of [3, 5, 8, 10, 12] = 8

### Mode

The number that appears most often in your dataset.

- **Example**: Mode of [2, 3, 3, 4, 5, 3] = 3 (it appears three times)

## Measures of Spread

### Range

The difference between the highest and lowest values.

- **Example**: Range of [5, 10, 15, 20] = 20-5 = 15

### Variance

Average of the squared differences from the mean. Shows how spread out numbers are.

1. Find the mean
2. Calculate each value's distance from mean and square it
3. Average these squared differences

- Higher variance = more spread out data

### Standard Deviation

The square root of variance. It's more practical because it's in the same units as your original data.

- Smaller standard deviation = data clustered closer to the mean
- Larger standard deviation = data more spread out

## Quartiles

Quartiles divide your data into four equal parts after arranging all values in order from lowest to highest.

### The Three Quartiles

**First Quartile (Q1):**

- The middle value between the smallest number and the median
- 25% of your data falls below this value
- Also called the 25th percentile

**Second Quartile (Q2):**

- The median of the entire dataset
- 50% of your data falls below this value
- Also called the 50th percentile

**Third Quartile (Q3):**

- The middle value between the median and the largest number
- 75% of your data falls below this value
- Also called the 75th percentile

### Example

For the dataset [3, 7, 8, 9, 12, 15, 18, 21, 25]:

- Q1 = 7.5 (between 7 and 8)
- Q2 = 12 (the median)
- Q3 = 19.5 (between 18 and 21)

## Interquartile Range (IQR)

The Interquartile Range is a measure of statistical dispersion that tells you the spread of the middle 50% of your data.

### Simple Definition

IQR = Q3 - Q1

Where:

- Q1 is the first quartile (25th percentile)
- Q3 is the third quartile (75th percentile)

### Why It's Useful

- **Resistant to outliers:** Unlike range, IQR isn't affected by extreme values
- **Measures variability:** Shows how spread out the core of your data is
- **Identifies outliers:** Values below Q1 - 1.5×IQR or above Q3 + 1.5×IQR are considered outliers

### Example

For the dataset [3, 7, 8, 9, 12, 15, 18, 21, 25]:

- Q1 = 7.5
- Q3 = 19.5
- IQR = 19.5 - 7.5 = 12

### In Box Plots

IQR is represented by the height of the box in a box plot, making it easy to visually compare data spread across different groups.

The IQR is particularly valuable when your data might contain outliers or when you want to understand the spread of the most typical values in your dataset.