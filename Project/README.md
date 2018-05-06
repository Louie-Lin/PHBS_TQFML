# Proposal

## Lin Liuyu 1701213060

## Project Description
The turn over of employee is what the employer concern. This project is to establish a model to predict whether employees will quit from a given record of factors affecting employee turnover.

## Dataset description

* __Dataset source__: [http://www.dcjingsai.com/common/cmpt/%e5%91%98%e5%b7%a5%e7%a6%bb%e8%81%8c%e9%a2%84%e6%b5%8b%e8%ae%ad%e7%bb%83%e8%b5%9b_%e8%b5%9b%e4%bd%93%e4%b8%8e%e6%95%b0%e6%8d%ae.html](http://www.dcjingsai.com/common/cmpt/%e5%91%98%e5%b7%a5%e7%a6%bb%e8%81%8c%e9%a2%84%e6%b5%8b%e8%ae%ad%e7%bb%83%e8%b5%9b_%e8%b5%9b%e4%bd%93%e4%b8%8e%e6%95%b0%e6%8d%ae.html) 
* __Dataset Information__: The data mainly include factors that affect employee turnover (salary, business travel, job satisfaction, work input, overtime, promotion, salary increase, etc.) And the corresponding record of employee turnover. The data is divided into training data and test data, which are stored in two files of pfm_train.csv and pfm_test.csv, respectively. The training data mainly consist of 1100 records and 31 fields. 

## 1.Data Vistualization
In the part, we will show the distribution of some features in these two kinds of employee.
 <div align="center">
<img width="512" height="256" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/data_visual1.jpg"/>
<img width="512" height="256" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/data_visual2.jpg"/>
<img width="512" height="256" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/data_visual3.jpg"/>
 </div>

* __Intuitive idea__: 
It seems that the younger or low salaries employees and those employees who usually work overtime have higher probability to quit.

## 2.Data Processing:

   * __2.1 Drop the meaningless columns__
   * __2.2 Deal with the NA data__
   * __2.3 Deal with the ordinal categorical data__
   * __2.4 Deal with the nominal categorical data__
   
## 3.Model Selection:

   * __3.1 Deal with imbalance data__
 <div align="center">
<img width="512" height="256" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/imbalance.jpg"/>
 </div>
    This is the number of two types people in the samples. 
    
    The target of the model training is to find a model which can predict whether the employee will quit. The most important thing is to figure out who will quit correctly so that the employer can have enough time to hire someone else to take his job and low down the cost. So it is necessary for us to solve the imbalanced data problem before we train model. We use __resampling method__ to solve this problem.
   
   * __3.2 Data split__
   * __3.3 Standardize the features__
   * __3.4 Do the PCA__
 <div align="center">
<img width="512" height="256" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/PCA.jpg"/>
 </div>
 
   We select 20 components to reach 90% of variance contribution.
   
   * __3.5 Model training__
   
   In this part, we train by __Logistic regression, SVM, K_Means, Decision Tree__ and find the best parameter of the model by accuracy.
   
 <div align="center">
<img width="400" height="400" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/ROC1.jpg"/>
 </div>
 
This is the ROC curve of four classifiers. The K_means perform well, its accuracy is more than 80%. The linear classfiers like Logistic regression, SVM perform badly, their accuracy is about 70%.

   __Conclusion:__ Logistic regression, SVM and Decision Tree do not perform well. K_Means performs well.

## 4.Improvement:

  * __4.1 Show the disadvantage of PCA__
  
In this part we take Logistic Regression as an example to show the disadvantage of PCA.

 <div align="center">
<img width="512" height="256" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/PCA example.jpg"/>
 </div>

This fiture is the classification results of Logistic regression in PC1, PC2. We can see that the PCA does not seperate the data linearly. So it is the main reason that why SVM, Logistic Regression will perform bad in training.

  * __4.2 Do the Kernel PCA to seperate the data in high dimention__
  
In this part, we use __rbf Kernel PCA__ to map the data from low dimention into high dimention.
  * __4.3 Test model by fitting the data after Kernel PCA__

<div align="center">
<img width="256" height="256" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/impove1.jpg"/>
<img width="256" height="256" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/impove1.jpg"/>
</div>
 
<div align="center">
<img width="256" height="256" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/impove3.jpg"/>
<img width="256" height="256" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/impove4.jpg"/>
</div>
 
 These are the 
  * __4.4 Test model stability by k-fold__
 <div align="center">
<img width="600" height="200" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/k_fold.jpg"/>
 </div>  
 
  * __4.5 Draw the ROC curve__
 <div align="center">
<img width="400" height="400" src="https://github.com/Louie-Lin/PHBS_TQFML/blob/master/Project/ROC2.jpg"/>
 </div>  
