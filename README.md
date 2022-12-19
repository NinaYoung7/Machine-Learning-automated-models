# Machine-Learning-automated-models

Submitted by: **NING YANG**

Time spent: **40** hours spent in total

Tools Used: R

This project is a part of Course APANPS5902 - DATA SCIENCE CONSULTING in Columbia University.


## Description

A social media client collects images that are uploaded by its users. Being able to automatically classify the images can help the client to gather information for marketing purposes. Using machine learning to accurately classify the images would be beneficial to this effort.

As a test case, we are focusing on images in the category of fashion products. However, we expect that implementing these models more broadly may be expensive and time consuming. With that in mind, our consulting company wants to recommend a modeling approach that limits the required sample size and processing time while still delivering good accuracy.

In addition to building the report, our team present recommendations on how to improve upon the infrastructure. We also identified opportunities for the client to make use of the information in novel ways. Then there will be an opportunity to inform our consulting company about the nature of the work and the considerations for a similar project in the future.


## Part 1: A Practical Machine Learning Competition

This part of the report will be directed externally to engineering teams throughout the client’s company. The idea is to give them the a useful technical product along with a report that evaluates the range of models that could be investigated. Keep in mind that the engineers are all excellent software developers but may lack familiarity with machine learning. Plan your communication accordingly.

### The Challenge:
What are the best machine learning models for classifying the labels of the testing set based upon the data of the training set? How small of a sample size do you need to generate good predictions? How long does the computer need to run to obtain these results? To balance these competing goals, we will introduce an overall scoring function for the quality of a classification:
Points = 0.15 * A + 0.1 * B + 0.75 * C  where

A is the proportion of the training rows that is utilized in the model. For instance, if you use 30,000 of the 60,000 rows, then A = 30,000 / 60,000 = 0.5;

B = min (1, ), where X is the running time of the selected algorithm in seconds. Algorithms that take at least 1 minute to run will have the value B = 1, which incurs the full run-time penalty.

C is the proportion of the predictions on the testing set that are incorrectly classified. For instance, if 1000 of the 10000 rows are incorrectly classified, then C = 1000 / 10000 = 0.1.


<img width="944" alt="Screen Shot 2022-12-19 at 4 14 56 PM" src="https://user-images.githubusercontent.com/103723722/208534203-b62b383b-cb91-4695-bf19-3dd82443dc55.png">





### Defining a Model: 
For our purposes, a model will be the use of a machine learning procedure with specific parameter settings. For instance, decision tree models and random forests are differing procedures that would each produce one model. Using a random forest with its default settings and separately with a different value of the ntree parameter would constitute two separate models.
Any single model can be applied to a data set of any size.

### Total Models: 

Multinomial logistic regression (Package: nnet; Function: multinom)

K-Nearest Neighbors (Package: class; Function: knn)

Classification Tree (Package: rpart; Function: rpart)

Random Forest (Package: randomForest; Function: randomForest)

Ridge, Lasso, or Elastic Net Regression (Package: glmnet; Function: glmnet with alpha = 0 for Ridge, alpha = 1 for Lasso, and values of alpha between 0 and 1 for Elastic Net)

Support Vector Machines (Package: e1071; Function: svm)

Generalized Boosted Regression Models (Package: gbm; Function: gbm or Package: xgboost; Function: xgboost)


### Samples: select 3 different sample sizes to work with.
For each selected sample size, you will generate 3 separate model development sets by sampling from the rows of the overall training data randomly without replacement. (You may use the sample function in R.) If the full sample size of the training data is selected, then please select your three model development sets by drawing randomly with replacement from the full training data set. As an example, you may consider using the following table names to create the 9 model development data sets:

<img width="445" alt="image" src="https://user-images.githubusercontent.com/103723722/208536788-fd4c51bb-e0fb-40e9-b9fa-9fd75da3bd22.png">


### Applying the Models: 
Implementation: On each of the 9 model development data sets, you will conduct the following work:
Fit all 10 of the selected classification models.

This means that a total of 90 separate models will be implemented.

Evaluation

For each of the 90 fitted models, the sample size proportion A, the running time score B, and the misclassification rate C will be computed and recorded.

The misclassification rate will be based on the model’s predictions on the testing set.

You will then compute the score for the model at that sample size using the scoring formula

Points = 0.15 * A + 0.1 * B + 0.75 * C


### Preliminary Results

With selected sample sizes of 500, 1000, and 2000, the results of the 90 models may be recorded as follows.

### A Scoreboard:

We will evaluate the results of a model at a selected sample size by calculating the average results across the 3 randomly sampled data sets. To do this, compute the means of A, B, C, and Points grouped by the Model and Sample Size.
Then you will report an overall scoreboard of your average results for the 30 combinations of Model and Sample Size.  The table below shows an example for the first 9 of the 30 combinations.

## Part 2: Additional Analyses

This part of the report will be directed externally to the managers of the engineering teams in the client’s company. 


## Part 3: Opportunities

This part of the report will be directed externally to the client’s senior leadership.The work will help to determine the future direction of the project and the company’s contract with this client. 



## Part 4: Part 4: Internal Wrap-Up

This part of the report will be directed internally to your consulting company’s managers and partners.

How would you summarize the nature of this engagement to your consulting company? Your engagement manager and the managing partners of the firm would be interested in how to improve their own approach to designing similar contracts in the future. Please answer the following questions.



## License

    Copyright [2022] [NING YANG]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

