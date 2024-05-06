# XGBoost Model for Online Order and User Churn Prediction

## XGBoost Model & Data

XGBoost Website: https://xgboost.readthedocs.io

To install the XGBoost model, we can use the pip installation method, for example, in the Windows operating system, Win+R shortcut keys to bring up the run box, enter cmd, enter the code in the pop-up interface and run: `！pip install xgboost`

The data used come from an online travel agency(OTA), and the XGBoost model was employed to predict user order and user churn.
Data and Data Description Catalog of **XGBoost for User Churn Prediction** is accessible through this link: https://drive.google.com/drive/folders/1D3boa4qNm-v0w3xFEaV3aWexcZudLFfc?usp=sharing


## XGBoost for Deal Prediction 
### Workflow
- Define the problem
- Data Collection
- Data Cleaning
- Feature Engineering and Processing
- Model Training
- Evaluation and Tuning
- Model Application 

## XGBoost for User Churn Prediction 
### Workflow
- Data Pre-processing
- Correlation Analysis
- Dimension Reduction(PCA)
- Data normalization
- Model Training and Evaluation
- Feature Engineering 
- RFM Modeling and User Profiling
- RFM Analysis
- According Strategy

### Hotel Info Correlation Heatmap
![Hotel Info Correlation Heatmap](https://github.com/peijin0405/ML-XGBoostModel-for-Deal-and-User-Churn-Forecast/assets/89746479/64a9e404-1c8b-47d6-b6b8-ce13588abbd6)

### User Feature Correlation Heatmap
![User Feature Correlation Heatmap](https://github.com/peijin0405/ML-XGBoostModel-for-Deal-and-User-Churn-Forecast/assets/89746479/de2db495-b104-4245-bb2e-e3278b387d8a)

### Feature Importance Chart
![Feature Importance Chart](https://github.com/peijin0405/ML-XGBoostModel-for-Deal-and-User-Churn-Forecast/assets/89746479/9b8906d1-cd87-4d10-974e-312997c1431d)

Important features: whether to visit the order filling page in 24 hours (iforderpv_24h), the number of daily average user visits to hotels in the last 3 months (historyvisit_avghotelnum), the current hotel conversion rate (hotelcr), the current hotel historical order cancellation rate (ordercanceledprecent), the starprefer, cancellationrate, historyvisit_visit_detailpagenum, price_sensitive, hoteluv, most viewed hotels businessrate_pre).

### RFM Model 
* R(Rencency): Last consumption
* F(Frequency): Consumption frequency
* M(Monetary): Spending amount

The values of **lasthtlordergap (time since last order)**, **ordernum_oneyear (number of user annual orders)**, and **consumption_level (user consumption level)** are chosen as R, F, and M, respectively, for clustering the user groups.

### Customer Segmentation
![Customer Segmentation](https://github.com/peijin0405/ML-XGBoostModel-for-Deal-and-User-Churn-Forecast/assets/89746479/710992c6-67ac-4a01-aad8-c8eb5abd42b2)

* Potential customers accounted for 12.3%, these customers are with poor RFM index scores, and are potential customers to be developed; 
* High-Value customers accounted for 11%; 10.1% of Key-Retention customers; 7% of Key-Developing customers. These are the customers worth noticing.

### User Profile Heatmap

<p align="center">
  <img src="https://github.com/peijin0405/ML-XGBoostModel-for-Deal-and-User-Churn-Forecast/assets/89746479/b5c238f4-f44f-47e4-ad0d-d3e0e6774c23" width="400" />
  <img src="https://github.com/peijin0405/ML-XGBoostModel-for-Deal-and-User-Churn-Forecast/assets/89746479/a9a9f34d-46d3-462e-899f-9a31357b759f" width="400" /> 
</p>

* The R(lasthtlordergap) of Group2 users is -0.17, the score is very small(the smaller,the better), F(ordernum_oneyear) is 1.1, much higher, M(consumption_level) is 1.3 is also almost the highest. Obviously, Group2 customers are High-Value customers;
* Group0 users have the lowest customer value and consumption level values. We classify this subgroup as Low-Value customers;
* We classify Group1 as Medium-Value customers.


**High-Value customers analysis**

This group of customers have high consumption level, they pursue high quality hotels. They have high visit frequency and booking frequency. They have shorter booking, and they make decisions fast(the average daily number of visits is small), and have high order cancellation rate. This group of customers have prominent business attributes, may travel at any time, so they will not book in advance, and travel could be canceled at any time(high the hotel cancellation rate).

Most High-Value customers are old customers. They are sensitive to the price, meaning they prefer high cost-effective products. They may visit and book in the middle of the night or early morning. 

This group of customers are very important to the business, so we need to implement personalized marketing for them:
1. Provide customers with more information about the hotels where they travel;
2. Recommend good reputation, cost-effective business hotel/chain hotel to attract them;
3. Send reminding messages at 11:00, 17:00 and other small peak hours of daytime on non-working days.


**Medium-Value customers analysis**

This group of customers have low consumption level, and do not pursue high-quality hotels. Their visit frequency is high, and the time of advance booking is the longest among the three subgroups. These customers usually like to browse the hotel websites and spend a lot of time browsing before deciding which hotel to book. We can label this type of customer as "cautious" customers. We can reasonably infer that this type of customers is likely to book a hotel for the purpose of travel. For this group of customers, we need to:
1. Regularly send hotels information two or three weeks before holidays；
2. Send high-end hotels and local travel information to attract users' attention, because such customers are more likely to travel；
3. Cooperate with hotel agents in scenic areas to make personalized recommendations for such users; and recommend more hotels with relatively affordable prices.



**Low-Value customers analysis**

This group of customers have extremely low demanding for high-quality hotel. They preferer lower prices and have short decision time. They have low visit frequency and low reservations frequency. Many customers in this group are new customers. For this part of customers, we need to：
1. Do not spend too much marketing costs on this subgroup. Since most of the new users are potential customers, it is recommended to perform well on users' initial user experience (such as the initial consumption of discounts, subscribes, etc.), and also regularly push affordable hotels in order to cultivate customer consumption habit;
2. Send content such as big sale activities to attract their attentions；
3. Since this part of the users accounted for large proportion. We could conduct churn analysis based on the loss of this group to better understand the factors that lead to customer loss.
