# Introduction to Statistics - Summarized Notes

## Chapter 1: What is Statistics?

Statistics is the practice of collecting and analyzing data, divided into two main branches:

1. **Descriptive/Summary Statistics**: Describes or summarizes data
2. **Inferential Statistics**: Applies sample data results to a larger population

### Key Concepts:

- Statistics helps answer practical questions across society (salaries, customer inquiries, etc.)
- Limitations: requires specific measurable questions, can't determine causation

### Types of Data:

- **Numeric Data**:
    - Continuous (stock prices)
    - Interval/count (number of coffee cups)
- **Categorical Data**:
    - Nominal (eye color)
    - Ordinal (agreement levels)

### Measures of Center:

- **Mean**: Sum of values ÷ Count of values
- **Median**: Middle value when data is ordered
- **Mode**: Most frequent value

### Measures of Spread:

- **Range**: Maximum − Minimum
- **Variance**: Average of squared distances from the mean
- **Standard Deviation**: Square root of variance
- **Quartiles**: Splitting data into four equal parts
- **Interquartile Range (IQR)**: 3rd Quartile − 1st Quartile

## Chapter 2: What are the Chances?

### Probability Basics:

- **Probability of an Event**: Number of ways event can happen ÷ Total possible outcomes
- **Example**: P(heads) = 1/2 = 50%

### Independent vs. Dependent Events:

- **Independent Events**: Probability of second event doesn't change based on first event
- **Dependent Events**: Probability of second event is affected by first event's outcome

### Conditional Probability:

- **Formula**: P(A|B) = P(A ∩ B) ÷ P(B)
- Used when events are dependent

### Discrete vs. Continuous Distributions:

- **Discrete**: Distinct, separate outcomes (dice roll)
- **Continuous**: Any value within a range (waiting time)

### Probability Distributions:

- Describe probabilities for all possible outcomes
- **Expected Value**: Mean of a probability distribution
- Example: Expected value of fair die = (1×1/6) + (2×1/6) + ... + (6×1/6) = 3.5

### Law of Large Numbers:

- As sample size increases, sample mean approaches expected value

## Chapter 3: Probability Distributions

### Binomial Distribution:

- Probability of number of successes in sequence of independent events
- **Examples**: Coin flips, clinical trials
- **Parameters**: n (number of trials), p (probability of success)
- **Expected Value**: n × p

### Normal Distribution:

- Bell-shaped, symmetrical distribution
- **Key Properties**:
    - Total area = 1
    - Curve never reaches 0
    - Described by mean and standard deviation
- **Distribution Areas**:
    - 68% within 1 standard deviation
    - 95% within 2 standard deviations
    - 99.7% within 3 standard deviations

### Poisson Distribution:

- Models number of events in fixed time period
- Used for random events with known average rate
- **Parameter**: λ (lambda) = average number of events per interval
- **Examples**: Restaurant arrivals, website visits

### Central Limit Theorem:

- As sample size increases, sampling distribution approaches normal distribution
- Applies to means and proportions
- Requires random, independent samples

## Chapter 4: Hypothesis Testing

### Key Concepts:

- **Null Hypothesis**: Assumes no difference exists
- **Alternative Hypothesis**: Proposes a difference exists
- **Independent Variable**: Not affected by other data (treatment)
- **Dependent Variable**: Affected by other data (response)

### Hypothesis Testing Workflow:

1. Define target populations
2. Develop null and alternative hypotheses
3. Collect/access sample data
4. Perform statistical tests
5. Draw conclusions

### Experiments:

- **Controlled Experiments**: Use treatment and control groups
- **Randomized Controlled Trial**: Random assignment to groups
- **Blinding**: Participants don't know which group they're in
- **Double-Blind**: Neither participants nor administrators know

### Correlation:

- **Pearson Correlation Coefficient**:
    - Measures relationship strength between variables (-1 to 1)
    - Magnitude = strength, sign = direction
- **Important**: Correlation ≠ causation
- **Confounding Variables**: Unmeasured factors affecting relationships

### Interpreting Results:

- **p-value**: Probability of achieving results if null hypothesis is true
- **Significance Level (α)**: Threshold for rejecting null hypothesis (typically 0.05)
- **Statistical Significance**: When p ≤ α
- **Type I Error**: Rejecting a true null hypothesis
- **Type II Error**: Failing to reject a false null hypothesis