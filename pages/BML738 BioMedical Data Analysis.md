# Lecture 1
	- [[Data Analysis]]
- # Lecture 2
  collapsed:: true
	- ## Structure
		- Minor 30
		- Major 45
		- Assignment 25
	- ## Matter
		- Paracetamol or Ibuprofen
		- Body temperature data - effect of anger on body temperature
		- Control Group - test group
		- Paired study
		- Statistical significance
		- In cancer Cells, as they are aggressive, more blood flow will be there
		- Bio-mechanics - Gait Analysis
			- What posture gives best outcome for fast bowlers
			- Predicting parkinsons
	- ## Data
		- Qualitative vs Quantitative
		- Subjective vs Objective
- # Lecture 3
  collapsed:: true
	- Biomedical Data Sources
		- Height, Weight, Glucose level
		- ECG, Cancer imaging
		- Gait Data, sensor output
	- types:
		- Direct measurement, semi-quantitative, quantitative
		- needs to be summarised
	- Population vs. sample data
		- Example -Exit Polls vs Actual election results
		- Sample selection is very important
			- should be representative
			- should not be biased
		- Sample data is used to draw inferences about the population
		- statistics
			- Descriptive - mean, median, mode, std dev, range, percentile, quartile, variance, expected value, skewness(left skewed or right skewed), kurtosis(narrow peak or wide flat), inter quartile range(Q3-Q1)
			- plots - Box and whisker plot(whisker is Q1-1.5IQR and Q3+1.5IQR) - 3 standard deviation rule - approx 99.7%
			- Why 1.5IQR?
			- Why when taking sample n-1 is taken instead of n?
				- When calculating sample variance, "n-1" is used instead of "n" because ==dividing
				   by "n-1" provides a more accurate estimate of the population variance 
				  by correcting for the bias introduced when using only a sample==; this
				   is often referred to as "Bessel's correction" and is related to the 
				  concept of "degrees of freedom" where the last data point in a sample is
				   not "free" to vary once the mean is calculated from the other data 
				  points.
		- Stats
			- Mean, SD
			- Series
				- Spatial -> Series
				- Time -> Series
			- Variables
				- Univariate
				- Multivariate
		- Data Types
			- Categorical - No Hierarchy, Ordinal
			- Quantitative - Discrete, Continuous
		- Data Issues
			- Different Standards
			- Bias
			- Accuracy of Info
			- Null/Missing values
		- Inferential
			-
		-
- # Lecture 4 [[BML738 BioMedical Data Analysis]]
	- {{today}}
	- Box and whisker plot
		- Q3+1.5IQR, Q3, Q2(median), Q1, Q1-1.5IQR
	- Histogram
		- label range, frequency of each label (for descrete data)
		- types: standard or normalized(freq/ y axis-> 0 to 1)... normalized freq becomes probability
		- Frequency distribution follow normal or gaussian distribution
		- For example, the PDF(probability density function) of a normal distribution is:
		  $$f_{X}(x)=\frac{1}{\sqrt{2\pi\sigma^2}}\exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right),$$
		- for standard normal distribution $z=\frac{x-\mu}{\sigma}$  N(0,1)
		- **68-95-99.7 Rule** or the **Empirical Rule**.
			- one std dev = 68.27
			  two std dev = 95.45
			  thre std dev = 99.73
		- Instead of using min max... use 1st percentile - 99th percentile
		- Skewness
			- Positive skewness -> mean>median
			- negative skewness ->mean < median
			- Non-parametric measure = 3(mean-median)/SD
			-
		- Kurtosis
			- whether data is heavy tailed or light tailed
			- The kurtosis of a random variable \( X \) is given by:
			  \[
			  \text{Kurtosis} = \frac{\mathbb{E}[(X - \mu)^4]}{\sigma^4},
			  \]
			- **Leptokurtic, mesokurtic, platykurtic**
		- Repeatability or Reproducibility of a measurement
			- Repeatability -> same experiment with same setup -> same result
			- Reproducibility -> same result can be obtained by diff team using same instrument
		- | **Aspect**         | **Reproducibility**                         | **Repeatability**                         |
		  |---------------------|---------------------------------------------|-------------------------------------------|
		  | **Focus**          | Between different setups or conditions      | Within the same setup or conditions       |
		  | **Scope**          | Measures generalizability                  | Measures precision                        |
		  | **Variability**    | Includes operator, environment, and equipment changes | Assumes identical operator, environment, and equipment |
		  | **Purpose**        | Validates reliability across studies        | Validates precision in one setup          |
			-
	- # Lecture 5
		- Review
			- Data distribution
			- Skewness, kurtosis
			- Reproducibility vs repeatability
		- Coefficient of variation (CV)
			- $CV=\frac{\sigma}{\mu}\cdot100$
			- In lab, the CV is preferred when the SD increases in proportion to concentration
			- at some places CV may be correct and constant and at other places SD
		- Correlation coeff
			- Two types - Pearson and spearman
			- | Feature                          | Pearson's Correlation Coefficient | Spearman's Rank Correlation Coefficient |
			  |----------------------------------|------------------------------------|-----------------------------------------|
			  | **Type of Relationship**         | Linear                           | Monotonic                              |
			  | **Data Requirements**            | Continuous and normally distributed | Ranked or non-parametric data          |
			  | **Scale Sensitivity**            | Sensitive to outliers            | Less sensitive to outliers             |
			  | **Calculation Basis**            | Raw data values                  | Ranks of data values                   |
			  | **Use Cases**                    | Measuring linear relationships in scientific or engineering data | Understanding ordinal or monotonic relationships in non-parametric data |
			-
- # Lecture 6 [[Jan 23rd, 2025]]
- Bland-altman plot for comparing tests or one test w.r.t golf standard
- z table, t table, f table
- 95% CI= 1.96 SD from z table
- TODO Steps to construct Bland and Altman methodology
- t test tells us whether it is ok to have outliers
	- 1 tailed
	- 2 tailed - paired. Unpaired
- | **Aspect**         | **Z-Test**                                                                 | **T-Test**                                                    | **F-Test**                                                  |
  |---------------------|---------------------------------------------------------------------------|--------------------------------------------------------------|------------------------------------------------------------|
  | **Purpose**         | Compares sample mean to population mean with known population variance.  | Compares means of one or two samples (independent or paired). | Compares variances of two or more groups.                 |
  | **Distribution**    | Standard normal distribution (Z-distribution).                          | T-distribution (varies with degrees of freedom).             | F-distribution (varies with degrees of freedom).          |
  | **Usage**           | Large sample sizes (n > 30) or known population variance.               | Small sample sizes (n ≤ 30) or unknown population variance.  | Testing equality of variances or in ANOVA.                |
  | **Example**         | Testing if a coin is biased.                                            | Testing if two teaching methods yield the same average score.| Testing variance of production in different plants.        |
  | **Assumptions**     | Normal distribution, known variance.                                    | Normal distribution, independent samples, equal variances.   | Independent samples, variances are normally distributed.  |
  | **Test Statistic**  | \( Z = \frac{\bar{X} - \mu}{\sigma / \sqrt{n}} \)                       | \( t = \frac{\bar{X} - \mu}{s / \sqrt{n}} \)                | \( F = \frac{\text{Variance of group 1}}{\text{Variance of group 2}} \) |
  | **Applications**    | Hypothesis testing, quality control.                                    | Hypothesis testing, comparing means.                         | Analysis of Variance (ANOVA), regression analysis.         |
- # Lecture 13 [[Feb 6th, 2025]]
	- Dynamic Data
		- Contrast Agent or Tracer
		- Glucose level