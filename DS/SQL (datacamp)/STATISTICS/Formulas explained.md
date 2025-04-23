# Statistical Formulas Made Simple

## Basic Probability

- **Probability of Event**: P(event) = Number of ways event can happen ÷ Total possible outcomes
    
    - _Explanation_: Shows how likely something is to happen by comparing how many ways it can happen to all possibilities. Ranges from 0 (won't happen) to 1 (certain).
- **Example**: P(heads) = 1/2 = 50%
    
    - _Explanation_: A coin has two sides, and heads is one of them, so the chance is 1 out of 2, or 50%.

## When Events Affect Each Other

- **Conditional Probability**: P(A|B) = P(A and B) ÷ P(B)
    - _Explanation_: Finds the chance of A happening when you know B already happened. Like finding the chance of rain when you know it's cloudy.

## Average Outcome

- **Expected Value**: E(X) = Sum of (each outcome × its probability)
    
    - _Explanation_: Shows what value you'd expect on average after many tries. Like the average score if you rolled a die many times.
- **Example (Die)**: E(X) = (1×1/6) + (2×1/6) + (3×1/6) + (4×1/6) + (5×1/6) + (6×1/6) = 3.5
    
    - _Explanation_: Each number on a die has a 1/6 chance. If you roll many times, your average roll will be about 3.5.
- **For Multiple Yes/No Events**: Expected successes = number of tries × chance of success
    
    - _Explanation_: If you flip a coin 10 times, you'll get about 5 heads because: 10 flips × 0.5 chance = 5.

## Finding the Middle

- **Mean**: Sum of all values ÷ Number of values
    
    - _Explanation_: The regular average - add everything up and divide by how many items you have.
- **Median**: Middle value when sorted
    
    - _Explanation_: Sort all numbers from smallest to largest and find the middle one. It's less affected by extreme values than the mean.
- **Mode**: Most common value
    
    - _Explanation_: The value that appears most often in your data.

## Measuring Spread

- **Range**: Highest value − Lowest value
    
    - _Explanation_: The full span from smallest to largest number in your data.
- **Variance**: Average of squared differences from the mean
    
    - _Explanation_: Shows how spread out numbers are from the average. Larger values mean more spread out data.
- **Standard Deviation**: Square root of Variance
    
    - _Explanation_: A more user-friendly measure of spread that's in the original units of your data.
- **Interquartile Range**: Middle 50% range = Q3 − Q1
    
    - _Explanation_: The range of the middle half of your data, ignoring the highest and lowest 25%.

## Bell Curve Facts

- 68% of data falls within 1 standard deviation of the mean
    
    - _Explanation_: About 2/3 of values are close to the average.
- 95% of data falls within 2 standard deviations
    
    - _Explanation_: Almost all values are fairly close to the average.
- 99.7% of data falls within 3 standard deviations
    
    - _Explanation_: Almost every value is somewhat near the average.

## Finding Chances in Ranges

- **Equal Chance Throughout Range**: P(between a and b) = (b - a) ÷ total range
    
    - _Explanation_: When all values in a range have equal chance (like arrival times), divide the section you want by the total range.
- **Example**: P(wait 4-7 minutes) = (7-4) ÷ 12 = 3/12 = 0.25
    
    - _Explanation_: If waiting times are equally likely between 0-12 minutes, the chance of waiting 4-7 minutes is 25%.

## Finding Opposite Chances

- P(greater than a) = 1 − P(less than or equal to a)
    - _Explanation_: To find the chance something is above a value, subtract the chance it's below that value from 1.

## Big Sample Rule

- As you collect more samples, the average gets more predictable
    - _Explanation_: The more times you repeat something (like flipping a coin), the closer your average results will be to the expected value.

## Making Decisions from Data

- If p-value ≤ significance level (usually 0.05), consider the result meaningful
    - _Explanation_: If the chance of seeing your results by random chance is very small (less than 5%), your findings are probably not just luck.