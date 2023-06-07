# CECS550_FinalProject
A project proposal for Pattern Recognition

DataSet link - https://csulb-my.sharepoint.com/personal/rahuldeo_vishwakarma01_student_csulb_edu/_layouts/15/onedrive.aspx?ga=1&id=%2Fpersonal%2Frahuldeo%5Fvishwakarma01%5Fstudent%5Fcsulb%5Fedu%2FDocuments%2FCECS550&view=0 

 ![image](https://user-images.githubusercontent.com/21274265/233248898-72861fc6-2c89-4671-ae74-eed4146aab99.png)
![image](https://user-images.githubusercontent.com/21274265/233248949-15ed58ef-c000-439c-85f0-31f90dcc8161.png)
![image](https://user-images.githubusercontent.com/21274265/233248967-e5bf9755-f329-4a7b-b725-155eeb85374c.png)
![image](https://user-images.githubusercontent.com/21274265/233248993-cad3fd98-4b1d-47c8-bb02-c480077f3920.png)

Repeat Buyers prediction for E-Commerce

1.	Problem statement 

Merchants often gain many new customers through promotions, but a significant portion of these customers are only interested in one-time deals. Therefore, the impact of promotions on long-term sales may be limited. To maximize return on investment (ROI) and reduce promotion costs, it is crucial for merchants to distinguish between one-time buyers and potential loyal customers and focus their efforts on converting the latter group.

In this project, you are provided a dataset with information on promotional shopping event from e-commerce platform. Your task is to design a system which will increase the ROI (in other words, you need to predict the probability that these new buyers would purchase items from the same merchants again within 6 months), reduce promotional cost, and identify one-time buyers. 

2.	Data description

The data set contains anonymized users' shopping logs in the past 6 months before and on the "Double 11" day (Promotional Event), and the label information indicating whether they are repeated buyers. But it will not affect the applicability of the solution. The files for the training and testing data sets can be found in "data_format2.zip". 

Details of the data format can be found in the table below.

Note: It is up to you to use any of the dataset format 1 or 2 as they both have similar information. 

Data Fields	Definition
user_id	A unique id for the shopper.
age_range	User' s age range: 1 for <18; 2 for [18,24]; 3 for [25,29]; 4 for [30,34]; 5 for [35,39]; 6 for [40,49]; 7 and 8 for >= 50;
0 and NULL for unknown.
gender	User' s gender: 0 for female, 1 for male, 2 and NULL for unknown.
merchant_id	A unique id for the merchant.
label	Value from {0, 1, -1, NULL}. ' 1' denotes ' user_id' is a repeat buyer for ' merchant_id' , while ' 0' is the opposite. ' -1' represents that ' user_id' is not a new customer of the given merchant, thus out of our prediction. However, such records may provide additional information. ' NULL' occurs only in the testing data, indicating it is a pair to predict.
activity_log	Set of interaction records between {user_id, merchant_id}, where each record is an action represented as ' item_id:category_id:brand_id:time_stamp:action_type' . ' #' is used to separate two neighbouring elements. Records are not sorted in any particular order.




3.	Data in another format

We also provide the same data set in another format, which contains 4 files and may be more user-friendly for feature engineering (files can be found in "data_format1.zip"). The details of the data formats can be found below:


User Behavior Logs

Data Fields	Definition
user_id	A unique id for the shopper.
item_id	A unique id for the item.
cat_id	A unique id for the category that the item belongs to.
merchant_id	A unique id for the merchant.
brand_id	A unique id for the brand of the item.
time_tamp	Date the action took place (format: mmdd)
action_type	It is an enumerated type {0, 1, 2, 3}, where 0 is for click, 1 is for add-to-cart, 2 is for purchase and 3 is for add-to-favourite.

User Profile

Data Fields	Definition
user_id	A unique id for the shopper.
age_range	User' s age range: 1 for <18; 2 for [18,24]; 3 for [25,29]; 4 for [30,34]; 5 for [35,39]; 6 for [40,49]; 7 and 8 for >= 50;0 and NULL for unknown.
gender	User' s gender: 0 for female, 1 for male, 2 and NULL for unknown.

Training and Testing Data

Data Fields	Definition
user_id	A unique id for the shopper.
merchant_id	A unique id for the merchant.
label	It is an enumerated type {0, 1}, where 1 means repeat buyer, 0 is for non-repeat buyer. This field is empty for test data.