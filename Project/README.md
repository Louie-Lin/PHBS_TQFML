# Proposal

## Lin Liuyu 1701213060

## Project Description

Credit card default is commonly problem and how to it will influenced the banks’ Rate of Bad Account, so it is important for the bank to make a good decision whether or not continue to provide a credit line to a person. This project is to analyze the dataset which contains some information of the historical behavior of people and try to get out a prediction model to figure out whether or not one person will default next month.

## Project process

* __Data analysis__: Do some statistical analysis on the data as well as visualize the data to get the intuitively idea that which feature may be useful to clarify these two kinds of people. For example, we can see the distribution of different features in these two kinds of people. 
*	__Data processing__: Deal with the __NA__ data. Consider about delete some data that is meaningless and only a small fraction of the whole data. For example, in feature __‘EDUCATION’__, the data of type __4, 5, 6__ (which mean ‘others’ or ‘unknown’) is only 1.5% of the whole data, which do not means the higher level of education and will lead to bias when predict by this feature and we should drop it out without too much information loss.
* __Feature construction__: Try to build some new features by the raw data to describe the behavior of this person more specific.
* __Data Split__:Spilt the data into training data and test data randomly.
* __Model Training__: Use the in-sample data to train and validate the model, I may use perception, logistic regression, SVM, decision tree and combine different models for ensemble learning to improve the performance.
* __Improvement__: Try to use PCA or LDA and redo the step of __Model training__.
* __Visualization__: Do some visualization for the outcome.
* __Evaluation__: Evaluate the clarification model by confusion metric and so on.

## Dataset description

* __Dataset source__: [https://www.kaggle.com/uciml/default-of-credit-card-clients-dataset](https://www.kaggle.com/uciml/default-of-credit-card-clients-dataset) 
* __Dataset Information__: This dataset contains information on default payments, demographic factors, credit data, history of payment, and bill statements of credit card clients in Taiwan from April 2005 to September 2005.
* __Data Variables__:
  * __User information__
    * __ID__: ID of each client
    * __LIMIT_BAL__: Amount of given credit in NT dollars (includes individual and family/supplementary credit)
    * __SEX	Gender__: (1=male, 2=female)
    * __EDUCATION__: (1=graduate school, 2=university, 3=high school, 4=others, 5=unknown, 6=unknown)
    * __MARRIAGE__:	Marital status (1=married, 2=single, 3=others)
    * __AGE__: Age in years
 
  * __User beahavior__
    * PAY_0	Repayment status in September, 2005 (-1=pay duly, 1=payment delay for one month, 2=payment delay for two months, ... 8=payment delay for eight months, 9=payment delay for nine months and above)
    * PAY_2	Repayment status in August, 2005 (scale same as above)
    * PAY_3	Repayment status in July, 2005 (scale same as above)
    * PAY_4	Repayment status in June, 2005 (scale same as above)
    * PAY_5	Repayment status in May, 2005 (scale same as above)
    * PAY_6	Repayment status in April, 2005 (scale same as above)
    * BILL_AMT1	Amount of bill statement in September, 2005 (NT dollar)
    * BILL_AMT2	Amount of bill statement in August, 2005 (NT dollar)
    * BILL_AMT3	Amount of bill statement in July, 2005 (NT dollar)
    * BILL_AMT4	Amount of bill statement in June, 2005 (NT dollar)
    * BILL_AMT5	Amount of bill statement in May, 2005 (NT dollar)
    * BILL_AMT6	Amount of bill statement in April, 2005 (NT dollar)
    * PAY_AMT1	Amount of previous payment in September, 2005 (NT dollar)
    * PAY_AMT2	Amount of previous payment in August, 2005 (NT dollar)
    * PAY_AMT3	Amount of previous payment in July, 2005 (NT dollar)
    * PAY_AMT4	Amount of previous payment in June, 2005 (NT dollar)
    * PAY_AMT5	Amount of previous payment in May, 2005 (NT dollar)
    * PAY_AMT6	Amount of previous payment in April, 2005 (NT dollar)
  * Default or not.next month
    * default.payment.next.month	Default payment (1=yes, 0=no)



