# Lecture 1
	-
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
			-
			-
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
	- ## Lecture 5
		- Review
			- Data distribution
			- Skewness, kurtosis
			- Reproducibility vs repeatability
		- Coefficient of variation (CV)
			- $CV=\frac{\sigma}{\mu}\cdot100$
			- In lab, the CV is preferred when the SD increases in proportion to concentration
			- at some places CV may be correct and constant and at other places SD
-