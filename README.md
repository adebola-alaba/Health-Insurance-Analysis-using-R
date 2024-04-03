# Insurance-Analysis-using-R

### <ins>Dataset Description</ins>
The dataset used is an insurance dataset with 1338 observations that originated from the United States of America. It contains no null value and has the following features: 

- Age: The primary beneficiary's age (excluding those above 64 years, since the government generally covers them).
- Sex: This gender of the policyholder, either male or female.
- BMI: measures how overweight or underweight a person is to their height. Weight in kilogrammes divided by height in metres squared gives you your BMI.
- Children: The number of dependents covered by the insurance policy.
- Smoker: - This represents how frequently the insured smokes; this answer can be either yes or no.
- Region: This refers to the beneficiary's residence in one of the four geographic regions of the United States: northeast, southeast, southwest, or northwest.
- Charges: Individual health insurance claims for medical expenses.
#### All variables are independent except Charges

### <ins>Confidence Interval</ins>
All tests will be carried out with a 95% confidence interval. This means if the p-value is below 0.05, the null hypothesis will be rejected and if it is above 0.05, then there is sufficient evidence not to reject the null hypothesis (i.e., it will fail to be rejected).

### <ins>Test for Normality</ins>
To be sure of the statistical test to be carried out, there is a need to carry out a test for normality. Primarily, the “BMI” and “Charges” dataset will be used for the statistical tests. For the normality test, the skewness test, boxplot, density distribution and Shapiro Wilk’s test was used. 

#### <ins>Normality Test for BMI Variable</ins>

#### 1. Research Question: is the BMI variable normally distributed?
- Ho: The BMI variable is normally distributed
- Ha: The BMI variable is not normally distributed

**Inference:** The skewness of BMI is [0.283410550996969]. The p-value of the BMI variable is 0.00002605. Since this value is less than 0.05, there is sufficient evidence to reject the null hypothesis. The BMI variable is not normally distributed.

#### <ins>Normality Test for Charges Variable</ins>
#### 2. Research Question: is the Charges variable normally distributed?
- Ho: The Charges variable is normally distributed
- Ha: The Charges variable is not normally distributed

**Inference:** The skewness of BMI is [1.51248251819953]. The p-value of the Charges distribution is 0.00000000000000022 This value is less than 0.05 and thus, there is sufficient evidence to reject the null hypothesis that the variable is normally distributed.

**Normality Conclusion:** Since the BMI and Charges variables do not follow the normal distribution, ***NON-PARAMETRIC TESTS*** will be used to statistically investigate the data.


### <ins>Non-Parametric Tests:</ins>

#### <ins>Two Sample Independent T-test:</ins>

**3. Research Question:** According to (NHS, 2022), the ideal BMI is between 18.5 and 24.9. Within this range, a person is healthy. People who smoke are said to have a lower BMI than those who do not smoke (Taylor, et al., 2019). ***Does the dataset support the claim that the average BMI of smokers is less than the average BMI of non-smokers?***
- Ho: The median BMI of smokers is higher than that of non-smokers
- Ha: The median BMI of smokers is not higher than that of non-smokers


**Inference:** With a p-value of 0.5321 which is greater than the significant level of 0.05, ***there is enough evidence for the null hypothesis to fail to be rejected. As seen, the median BMI of smokers is slightly higher than that of non-smokers.*** The non-smoker's mean BMI isn't within the ideal range. Not too much of a surprise here as "not smoking" is not the only remedy to having a healthy lifestyle. There are other factors such as healthy eating, exercise etc.



**4. Research Question: Are the insurance claims of smokers and non-smokers similar?**
- Ho: The insurance claims of smokers and non-smokers are similar
- Ha: The insurance claims of smokers and non-smokers are not similar

 

**Inference:** The p-value is below 0.05. Therefore, ***there is no sufficient evidence to fail to reject the claim that the charges of those who smoke, and non-smokers are the same.*** The null hypothesis is hereby rejected as the result shows that the claims are indeed different



### <ins>Pearson Chi-Squared Test</ins>

**5.	Research Question: Are smoking and region dependent? Does region influence the habit of smoking or not?**

- Ho: Region and smoking status are independent
- Ha: Region and smoking status are dependent
 
**Inference:** The chi-squared test shows that region and smoker are independent as the p-value > 0.05 thus the null hypothesis fails to be rejected.


### <ins>Kruskal-Wallis Test</ins>

**6.	Research Question: Do the regions differ from each other in terms of central tendency?**

- Ho: There is no significant difference in charges between the regions
- Ha: There is a significant difference in charges between the regions
 
**Inference:** This shows that the regions have a similar central tendency as the p-value > 0.05.



### <ins>Correlation Test</ins>

**7.	Research Question: Are any of the variables correlated?**

 <p align="center">
<img src="https://github.com/siraug/Health-Insurance-Analysis-using-R/assets/122705182/a5678de3-098e-43f4-9236-0d3959008b14" alt="Correlation Plot">
</p>


Inference: The results show that some variables are positively correlated:
-	 Smoker and Charges variables have a correlation coefficient of 0.66. This indicates a strong positive correlation. It is no surprise because the insurance claims of smokers are expected to be higher due to the resulting health conditions from smokers such as damaged lungs, dental conditions etc. 
-	Age and Charges have a correlation coefficient of 0.53. This supports the fact that as people grow older, they tend to need more medical attention. Hence the increase in charges as we grow older.

### <ins>Multiple Linear Regression</ins>
**8.	Research Question: is there any influence on charges when age and smoker are predictor variables?**
- Ho: There is no relationship between the predictors and response variables
- Ha: There is a relationship between the predictors and response variables

 <p align="center">
<img src="https://github.com/siraug/Health-Insurance-Analysis-using-R/assets/122705182/4f976ece-83ea-4560-9f02-d75815ab56f2">
</p>


