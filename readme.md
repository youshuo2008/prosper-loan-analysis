# Prosper Loan Data Exploration
## by Shuo You

## Date created
This project and README file were created on 09/27/2019.

## Dataset

The Prosper Loan dataset contains 113,937 loan records with 81 variables. <br />
The orginal dataset can be found at [here](https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv)
and the feature documentation is available at [here](https://docs.google.com/spreadsheets/d/1gDyi_L4UvIrLTEC6Wri5nbaMmkGmLQBk-Yx3z0XDEtI/edit#gid=0 "Prosper Load variable data dictionary"). <br />
For this project, I'm interested in comparing completed loans with defaulted loans, so a subset of data was selected. <br />
After data wrangling, my main dataset has 49640 loan records with two loan status groups: 'Completed' and 'Defaulted'. <br />
As Credit Grade and Prosper Rating features were used for loans originated before July 2009 and after July 2009 respectively, <br />
further subsetting of the main dataset was conducted. <br />

## Summary of Findings

I started my exploration with univariate distributions. I found the defaulted loan percentage is 30.8% and majority of the loans (90.8%) are in 36 months term. <br />
I also discovered about half (51.8%) of the loan borrowers do not own a house and most of the Borrower Rate falls between 0.05 and 0.35. <br />
Further, I revealed the distribution of Lender Yield is similar to the Borrower Rate with negative yields seen. Also, the distribution of Debt to Income Ratio was right-skewed. <br />
After 'log' scale transformation of x-axis, the Debt to Income Ratio generally follows a unimodal distribution with many spikes seen. Most of the Debt to Income Ratio falls below 1, <br />
with noticeable outliers on the right side of the distribution. Looking into the borrower income range showed us the most common two income ranges are $25,000-49,999 and $50,000-$74,999 <br />
though 14.9% of borrower's Income range were not displayed. Then I looked into original loan amount and monthly loan payment distributions. Both distributions were right-skewed, <br />
and after 'log' scale transformation of x-axis, several spikes were seen at $1000 increment levels within the original loan amount distribution while monthly loan payment follows a near normal distribution <br />
with most monthly payments between $30-$1000 per month. The credit grade distribution revealed the most common credit grade was level 'C', representing 20% of the loans. <br />
Second and third popular credit grades were grade 'D' (18.1%) and grade 'B'(15.0%) loans. 'HR', 'E', 'A', 'AA' levels loans were less common, at 11.4-12.1%. For prosper rating, the most common <br />
Prosper Rating loans was: rating 'D' loans (22.2%). 'HR', 'E', 'C', 'B', 'A' rating loans were between 13.2% to 14.7%. And highest rating 'AA' loans only represented 7.2% of the total loans. <br />
Moving forward, I started looking at relationships with Bivariate Exploration. I found Defaulted loan borrowers have slightly lower home ownership rates compared to Completed loan borrowers (45.6% vs 49.3%) <br />
and defaulted loans generally have higher borrower rates compared to the completed loans. However, the distribution for Debt to Income Ratio, Original loan amount, Monthly loan payment looks similar <br />
between the defaulted loans and the completed loans. When I looked at 'CreditGrade' and 'ProsperRating (Alpha)' between the two groups, I found that the defaulted loans have much higher percentage of <br />
lower grade loans ('HR' and 'E' grade loans) and much lower percentage of higher grade loans ('A' and 'AA' grade loans). This indicates lower Credit Grade/Prosper Rating loans ('HR' and 'E') tend to have <br />
higher default rate, and higher Credit Grade/Prosper Rating loans ('A' and 'AA') tend to have lower default rate. I also explored the relationship between 'BorrowerRate' and 'CreditGrade'/'ProsperRating (Alpha)'. <br />
I found that as 'CreditGrade' or 'ProsperRating (Alpha)' increases, the median borrower rate gradually decreases which is quite interesting. I also explored the relationship between 'LoanOriginalAmount' and <br />
'CreditGrade'/'ProsperRating (Alpha)' and found that as the 'CreditGrade' or 'ProsperRating (Alpha)' increases, the median original loan amount forms a general increases trend. Finally, I moved into Multivariate Exploration.<br />
I first explored the effects of Loan Status, Credit Grade/Prosper Rating on Borrower Rate. I found that for both the completed and defaulted loans, lower Credit grade 'HR' and 'E' loans have highest Mean Borrower Rate.<br />
And as Credit Grade increases in quality (from 'HR' to 'AA'), the Mean Borrower Rate tend to be lower (except for 'HR' vs 'E' loans). Interestingly, the defaulted loans have higher Mean Borrower Rate in every Credit Grade <br />
compared to the completed loans. I also discovered lower Prosper Rating 'HR' and 'E' loans have the highest Mean Borrower Rate. And as Prosper Rating increases in quality (from 'HR' to 'AA'), the Mean Borrower Rate <br />
became lower. Very interestingly, Defaulted loans also tend to have higher Mean Borrower Rate in every Prosper Rating category compared to the completed loans (except for 'HR' rating loans). Then I investigated <br />
the effects of Loan Status, Credit Grade/Prosper Rating on Original Loan Amount. I found a positive relationship between Credit Grade and Mean Original Loan Amount. As Credit Grade increases in quality, <br />
the Mean Original Loan Amount also increases in both the Defaulted and Completed loan groups. However for each Credit Grade, defaulted loans have higher Mean Original Loan Amount. And this trend is most obvious <br />
in grade 'B', 'A' and 'AA' loans. I also discovered as Prosper rating increases, the Mean Original Loan Amount also tend to increase in both the Defaulted and Completed loan groups. Compared to the completed loans, <br />
the defaulted loan group have a higher Mean Original Loan Amount. The differences are most obvious in the Prosper Rating 'B', 'A' and 'AA' loans. I noticed the Mean Original Loan Amount differences between defaulted <br />
and completed loans for Credit Grade 'B', 'A' and 'AA' loans were larger. Finally, I looked into the effects of Loan Status, Credit Grade/Prosper Rating on monthly loan payment. I saw a positive relationship between <br />
Credit Grade and Mean Monthly Loan Payment amounts. As Credit Grade increases in quality, the Mean Monthly Loan Payment amount also increases in both the completed and defaulted loans. Defaulted loans indeed have <br />
higher Mean Monthly Loan Payment in every Credit Grade sub-group. Again, the differences are most obvious in Grade 'B', 'A' and 'AA' loans. I also found that as Prosper Rating increases from 'HR' to 'C', <br />
the Mean Monthly Loan Payment also increases in both the completed and defaulted loan groups. However, there is a slight decrease in Mean Monthly Loan Payment for rating 'A' loans, then another increase for 'AA' loans.<br /> Compared to the Completed loan group, the Defaulted loans only have a slight increase in Mean Monthly Loan Payment in Prosper Rating 'HR', 'E', 'D', 'C', 'A', 'AA' loans. And for 'B' rating loans, <br />
the Mean Monthly Loan Payment is actually lower in the Defaulted group.  


## Key Insights for Presentation

For the presentation, I focused on exploring the effects of loan status, credit grade/Prosper Rating on borrower rate. <br />
I first introduced the borrower rate variable by presenting its distribution. Then, I compared the borrower rate between <br />
the defaulted and completed loan groups and found the Defaulted loan group generally have higher borrower rates. <br />
Afterwards, I looked into the relationship between Credit Grade and Borrower Rate as well as relationship between Prosper Score <br />
and Borrower Rate. I discovered higher Credit Grade or higher Prosper rating borrowers tend to have lower Borrower Rate. <br />
Then I investigated the effects of Loan Status, Credit Grade/Prosper Rating on Borrower Rate with two multivariate point plots. <br />
Interestingly, I found the defaulted loan group tend to have higher Mean Borrower Rate in every Credit Grade/Prosper Rating <br />
compared to the completed loans.


## Credits

For this project I used the below websites to create my submission:

https://stackoverflow.com

https://matplotlib.org

https://seaborn.pydata.org/


I wanted to specially say thank you to my Udacity mentor: Raj V and Udacity project reviewers for their strong support.
