# Flipkart Marketing Analytics
Flipkart is currently the largest e-commerce retailer in India. To retain its position as India’s largest e-commerce retailer and stay ahead of competition, it is crucial for Flipkart to plan and utilise its marketing budget more efficiently. This can be achieved by designing customised marketing programs to target specific customer segments based on their identified underlying needs.

### Objective
By analysing past customer transactional data, the purchase history can provide managerial insights on the customers. Customer segmentation helps to group customers with similar characteristics and allows us to calculate the Customer Lifetime Value (CLV), which provides an indication of how much value customers bring to the company in their entire stream of lifetime purchases. 

With a better understanding of the customers and their value contribution, marketing strategies can then be designed for identified attractive segments while ensuring that marketing costs are allocated efficiently to reap the highest returns.

### Research Question
How should Flipkart segment its customers and design targeted marketing strategies?


## Project Resources
This code documentation only provides a high level summary of the notebooks within the repository. More essential details and analysis conducted for this project are documented in the report linked [here](https://docs.google.com/viewer?url=https://raw.githubusercontent.com/gohjiayi/flipkart-marketing-analytics/master/docs/Flipkart-Marketing-Analytics_Report.pdf).


## Project Directory Structure
```
├── Data
│   └── ...
├── Data Cleaning & EDA (Purchase).ipnyb
├── Data Cleaning & EDA (Psychometric and Demographic).ipnyb
├── Data Preparation (Purchase).ipnyb
├── Data Preparation (Psychometric and Demographic).ipnyb
├── Factor Analysis.ipnyb
├── Linear Regression - RFM Weights.ipnyb
├── Customer Segmentation.ipnyb
├── Segment and Descriptor Differences.ipnyb
├── Classification Model.ipnyb
└── ...
```
This project is built on Python 3 and scripts were originally hosted on Google Colab. Required packages are installed individually in each `.ipnyb` file.

The `Data/` folder consists of the datasets used and generated.


## 1. Data Gathering, Cleaning & Exploration
The Flipkart data was retrieved from Kaggle - [chandanmalla/marketinganalyticsdata](https://www.kaggle.com/chandanmalla/marketinganalyticsdata). There are 2 datasets available: (1) purchase and (2) psychometric and demographic data.

Data cleaning and exploration was conducted on these 2 datasets in the `Data Cleaning & EDA (Purchase).ipnyb` and `Data Cleaning & EDA (Psychometric and Demographic).ipnyb` notebooks respectively.


## 2. Data Preparation
The cleaned data is then transformed into relevant variables for subsequent customer segmentation and analysis using domain knowledge.

### 2.1 Purchase Data
Data preparation for the purchase data includes the calculation of Recency, Frequency and Monetary Value for subsequent customer segmentation (RFM segmentation). The execution is detailed in the `Data Preparation (Purchase).ipnyb` notebook.

### 2.2 Psychometric and Demographic Data
To prepare the psychometric and demographic data, categorical variables were converted into numerical variables in the `Data Preparation (Psychometric and Demographic).ipnyb` notebook.

With the large number of variables, factor analysis was carried out to reduce dimensionality in the `Factor Analysis.ipnyb` notebook. Although these newly generated factors were not eventually used due to non-ideal results, they were used for comparison against the original segmentation and descriptor variables for insights.


## 3. Customer Segmentation
Customer segmentation was carried out using RFM segmentation.

### 3.1 Setting RFM weights
Although RFM weights for the segmentation could be set empirically based on the nature of the business and contextual knowledge, we have experimented with estimating using a Linear Regression model to estimate the weights instead as seen in the `Linear Regression - RFM Weights.ipnyb` notebook. However, due to the poor adjusted R squared value, the RFM weights were eventually set empirically without the use of the model developed.

### 3.2 RFM Segmentation
Using the RFM weights and variables generated in the previous stages, an RFM score could be generated for each customer. RFM segmentation is then conducted by using different cut-off RFM scores.

To identify the best number of segments for a relatively small dataset, managerial judgement together with numerical and strategic criteria were involved in the decision process. The customers were grouped into 2, 3, 4 and 5 segments and analysis was conducted to determine an ideal number of segments based on contextual knowledge. **4 segments** was chosen as the optimal number of segments.

A transition matrix across the 4 segments was generated to measure how customers have evolved from one segment to another across a time period of 3 months. The Customer Lifetime Value (CLV) of these customers were then calculated, providing an indication of how much value customers bring to the company in their entire stream of lifetime purchases.

The source code can be found in the `Customer Segmentation.ipnyb` notebook.


## 4. Segment and Descriptor Analysis
Based on the segments generated, the segmentation and descriptor variables were analysed to identify the unique characteristics of each segment where relevant marketing strategies can be developed as seen in the `Segment and Descriptor Differences.ipnyb` notebook.


## 5. Classification Model
Predicting the segment membership for new customers will be insightful for Flipkart to better tailor marketing campaigns to acquire and retain these individuals. Descriptor variables may be more easily obtained as compared to segmentation variables and thus, we have explored whether descriptors could be used to predict segment membership using a multinomial logistic regression model in the `Classification Model.ipnyb` notebook.


## Contributors
- Carine Tan - [@carine99](https://github.com/carine99)
- Goh Jia Yi - [@gohjiayi](https://github.com/gohjiayi)
- Koh Gladys - [@gladyskoh](https://github.com/gladyskoh)
- Koh Min - [@kohmin](https://github.com/kohmin)
- Loh Zi Ying - [@Mochihaha](https://github.com/Mochihaha)