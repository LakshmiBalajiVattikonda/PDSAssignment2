## Question 2 – Diabetes Dataset (diabetes.csv)

### Overall goal
Use sampling and bootstrap methods on the diabetes dataset to understand how sample statistics (mean, max, standard deviation, and percentiles) relate to the full population, and to see how sample size affects the stability of these estimates.

---

### 1. Random sample of 25 and comparison of mean and max Glucose


  Statistic      Sample Value   Population Value
  -------------- -------------- ------------------
  Mean Glucose   130.36         120.8945
  Max Glucose    197            199



**What I did**

1. I selected 25 random rows from the diabetes dataset using a fixed seed.

2. I calculated the mean and maximum Glucose values for this small sample.

3. I also calculated the population mean and max from all 768 rows.

4. I compared both using simple bar charts.

**Interpretation**

1. The sample mean and max values showed noticeable differences compared to the population values.

2. This demonstrates normal sampling variability — small samples often differ from the population.

3. The plots help illustrate whether the sample overestimates or underestimates the population.

4. Overall, the sample provides an approximation, but not a perfect representation of the population.

---

### 2. Comparing the 98th percentile of BMI (sample of 25 vs population)



  Statistic                Sample Value   Population Value
  ------------------------ -------------- ------------------
  98th Percentile of BMI   45.264         47.526



**What I did**

1. I calculated the 98th percentile of BMI from the sample of 25.

2. I calculated the same 98th percentile from the full population dataset.

3. I created a bar chart to compare both values.

4. This helped show how extreme percentiles behave with small samples.

**Interpretation**

1. The 98th percentile from the small sample was less reliable and differed from the population’s 98th percentile.

2. Percentiles, especially high ones (like 98th), require large sample sizes to be stable.

3. The sample percentile likely fluctuated more because only 25 observations were used.

4. This shows why large samples are better for percentile calculations.

---

### 3. Bootstrap (500 Samples of 150 Rows)



  Statistic (BloodPressure)   Bootstrap Average   Population Value
  --------------------------- ------------------- ------------------
  Mean                        69.1546             69.1055
  Standard Deviation          19.2049             19.356
  98th Percentile             98.0235             98.0

  

**What I did**

1. I generated 500 bootstrap samples, each containing 150 rows with replacement.

2. For every sample, I calculated the mean, standard deviation, and 98th percentile.

3. I stored all these results in lists.

4. Then I plotted histograms and compared them with population values.

**Interpretation**

1. Bootstrap results produced stable distributions centered around the population values.

2. Since 150 is a large sample, the bootstrap mean and SD stayed close to the population numbers.

3. The 98th percentile also aligned better than in part (b), proving that larger samples give more reliable percentile estimates.

4. The histograms showed tight clustering, confirming that bootstrap is effective for estimating sampling uncertainty.


### Overall takeaway from Question 2
- Small samples (like n = 25) can give rough estimates but show substantial variability, especially for extreme statistics like maxima and high percentiles.
- Bootstrap resampling helps us see how much our estimates might change from one sample to another.
- Increasing the sample size (to n = 150) narrows the bootstrap distributions, bringing estimates much closer to the true population values.
- Together, these experiments emphasize the importance of sample size and resampling methods in statistical inference.
'''