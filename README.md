# Module 17 Supervised Machine Learning
## Challenge: Credit Risk Analysis
### Background
The assignment states that "Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, we’ll need to employ different techniques to train and evaluate models with unbalanced classes." To solve this challenge, we are asked you to use imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.
For this project, we have been asked to use a dataset from from LendingClub.
We will use technologies such as Pandas, Google Colab, Jupyter notebook, PostgreSQL, AWS to mine the dataset. By doing so, we intend to meet this challenge's requirements, namely: <br/>
- extract the dataset,
- transform the data, 
- connect to an AWS RDS instance, and 
- load the transformed data into pgAdmin.
Finally, using PySpark, Pandas, or SQL we will determine whether there exists any bias toward "favorable reviews from Vine members in the chsen dataset".
### Actions and Results<br/>
#### Actions: Delivery 1
- Created a new database with Amazon RDS named [vinereviewdb](https://us-east-2.console.aws.amazon.com/rds/home?region=us-east-2#database:id=vinereviewdb;is-cluster=false),
- In pgAdmin, created a new database and linked it to Amazon RDS server,
- In pgAdmin created via a schema builder four tables to hold the data cleaned through our ETL process. These tables are: <ul><li>customers_table,</li> <li>products_table,</li> <li>review_id_table,</li> <li>and vine_table.</li></ul>
- Ran a script to populate these tables. The list below show the numbers of items loaded in each table:

  |table name|count|
  |---|-----|
  |customers_table|3467883|
  |products_table|1074867|
  |review_id_table|6221559|
  |vine_table|6221559|

### Actions: Delivery 2
|Review|Analysis Results|
|---|-----|
|data filtered by items with 20 or more votes|96370|
|data filtered by helpful_votes >= 50%|1448|
|data filtered by items with a Vine review|647|
|data filtered by items with no Vine review|90768

#### Results
|Review|Analysis Results|
|---|-----|
|The total number of reviews|92216|
|the number of 5-star reviews|647|
|the number of 5-star no reviews|44104|
|e percentage 5-star reviews|44.68232044198895|
|e percentage 5-star no reviews|48.589811387273045|

### Summary
The percentage difference between the reviews is about 4%. One may conclude that a positive bias favors the non-paid reviews.

 
