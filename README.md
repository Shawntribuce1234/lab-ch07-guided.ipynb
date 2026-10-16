Estimation & Bootstrapping — Quantifying Uncertainty Without a Formula
Objective
The goal of this lab was to understand how to measure uncertainty in statistical estimates using standard errors, confidence intervals, and bootstrapping.
Methodology
- Loaded the UCI Adult Census Income dataset containing 32,561 respondents.
- Compared standard deviation and standard error to understand how sample size affects the accuracy of an estimate.
- Tested the s/sqrt(n) relationship across four different sample sizes.
- Used the Central Limit Theorem (CLT) to calculate confidence intervals for age and capital gains.
- Created bootstrap samples manually and compared the results with scipy.stats.bootstrap.
- Compared percentile and BCa confidence intervals to see how they handle skewed data.
- Used bootstrapping to estimate the difference in average weekly working hours between men and women.
- Used AI to generate a bootstrap function, revised it, and compared its results with my own calculations.
- Ran a simulation using lognormal data to compare how often parametric and bootstrap confidence intervals captured the true mean and median.
Key Findings
- Standard deviation vs. standard error: I found that increasing the sample size reduces the standard error but not the standard deviation because standard error measures how precise our estimate is while standard deviation measures how spread out the data is.
- Central Limit Theorem: The CLT worked much faster for age because the data was less skewed, while capital gains needed larger samples before the distribution of sample means became approximately normal.
- Bootstrapping: I learned that bootstrapping allows us to estimate uncertainty by repeatedly sampling from the original dataset instead of relying on a formula.
- Median age: The bootstrap standard error for median age was 0.0000 because the dataset had so many repeated ages that every resample produced the same median. This showed that the bootstrap was reflecting the data rather than producing an error.
- Confidence intervals: I found that percentile and BCa intervals gave slightly different results for capital gains because the data was heavily skewed.
- Weekly working hours: Men reported an average of 42.43 hours per week compared to 36.41 hours for women, a difference of 6.02 hours. However, this doesn't mean gender directly causes the difference since other factors could influence working hours.
- AI verification: I learned that AI-generated code still needs to be checked because the AI initially guessed the random seed instead of using the lab's settings.
- Coverage simulation: At a sample size of 50, both the parametric and bootstrap intervals slightly underestimated uncertainty for the mean, with their difference falling within the Monte Carlo standard error of about 1.3 percentage points. For the median, the mean-centered parametric interval performed much worse while the bootstrap stayed closer to the expected 95% coverage.
Conclusion
This lab helped me understand why measuring uncertainty is important when working with data. I learned that larger samples can make estimates more precise, but the distribution of the data also matters when choosing a method. My biggest takeaway was that bootstrapping is useful because it allows us to estimate uncertainty even when we don't have a simple formula. I also learned that confidence intervals and AI-generated results should always be checked rather than automatically trusted.
