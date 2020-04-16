# capstone_nit-k

Objective

The team of data scientists' goal was to investigate the potential to invest in peer-to-peer loans. We wanted to find out what defines good loans and bad loans and construct loan portfolios with advanced return-risk profiles.

What is the Lending Club?

The Lending Club is one of the first peer-to-peer lending services and is still a major player in the marketplace. Instead of borrowing from a bank, borrowers can borrow from “investors” directly. It is often less expensive and potentially easier to qualify for.

How does it work?

The Lending Club offers individual and business loans. Individual loans range from $1,000 to $40,000 principal and have terms of 3 or 5 years. Borrower interest rates range from APR ( Annual Percentage Rate) 6.16% to 35.89%, depending on credit score, credit history, and past borrowing record. Investors can reserve “Notes” in increments as low as $25, which is quite an incentive for small investors. Diversified loan portfolios are expected to earn annual returns between 4% and 6%.

Data Analysis

As prospective lenders choosing from available borrowers, we started with a dataset of loans with 2.2 millions of observations and over 150 variables covering the years 2007 -2014. We narrowed the scope of our analysis by focusing on features only visible to investors and by downsampling our data. While computing return and default rates, we defined and analyzed some of the risks of the loan faced by investors.

Loans Risks for Investors

Based on the first analyses, we categorized the following types of loans as lower-risk and high-risk loans, considering that investors may want to minimize their risk exposure.

  Low-risk loans: Fully Paid
  High-risk Loans: Defaulted, Charged off, Settlement, In Grace Period, and Late Payments. 
 
Profit/Loss by term and grade

The longer the term of the loans is, the more likely investors are to lose or earn money. However shorter terms are safer investments (with smaller rewards).
Additionally, the graph in jupyter notebook displays that the grade is a significant factor that affects the returns of the loans.

Risk Factors

Upon performing a random forest model on loans from 2007 to 2015 (only completed loans) with features visible to investors, the result of features by importance showed that "debt-to-income" ratios or states the borrowers are located at, purposes of loans, or FICO score (consumer credit score) are significant indicators of risks of loans. The loans with high numbers of these indicators were more likely to be categorized as "default" loans. 

Portfolio building

Based on the above analysis, we created a selection of portfolios that considered features that signal risks of loans such as credit scores or debt to income ratio and filter them to offer a range of risks and returns by what investors are looking for. We targeted loans that were fully paid to understand each of the scenarios.

Portfolio Performances Compared

Risky (diversifying into high-interest loans) strategy often yields significantly higher returns than safer strategies, but the next question is: how can we mitigate the additional risk?

Modeling Default Likelihood of Low-Grade Loans

In order to increase the accuracy of the above portfolio, the data scientists of our team stack 7 binary classification models to predict defaulted loans. The important metric for this training was precision. We wanted to reduce false positives in predicting fully paid loans. The below chart shows testing precision for different years. 

Machine learning enhanced portfolio

By focusing on higher risk loans (grade D and below) and predicting their likelihood of default using various machine learning models, we successfully increased the returns of the portfolios. The resulting portfolio performance improved by 10%. The below chart compares "risky" portfolio includes predicted loans vs non-predicted loans by the model.

Conclusion

We recommend an investment strategy of diversifying overall, with the more low-risk loans selected by machine learning. Our future work would encompass model improvement and parameter tuning of the model.
