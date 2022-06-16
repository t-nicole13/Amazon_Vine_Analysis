# Amazon_Vine_Analysis

## Objective 
For this project, I wanted to analyze if there was any positivity bias if customers were paid to review products.  I chose the jewelry reviews dataset from Amazon Reviews to complete my analysis.  This dataset contains both paid and unpaid reviews.  The paid reviews are from customers who are apart of the Amazon Vine Program.  

Amazon Vine invites the most trusted reviewers on Amazon to post opinions about products to help their fellow customers make informed purchase decisions.    I used PySpark functions to determine if there is any bias toward favorable reviews from Vine members in the dataset. 

Additionally, I used PySpark to perform the ETL process to extract, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin for review.  


### Tasks
#### Perform ETL on Amazon Product Reviews
  1. Extracted the jewelry dataset into a Spark DataFrame.
  2. Created a customer's table DataFrame.
  3. Created a product's table DataFrame.
  4. Created the review id DataFrame.
  5. Combined columns from the previously created DataFrames to create a Vine table.
  6. Connected to the AWS RDS instance and loaded each DataFrame to its own table in pgAdmin.
  
#### Determine Bias of Vine Reviews
  1. Loaded previously created Vine table.
  2. Created a total votes DataFrame that have reviews with at least 20 votes, these reviews are most likely to be helpful.
  3. Created a helpful votes DataFrame that shows all rows where the number of helpful votes is equal to or greater than 50%.
  4. Created a paid DataFrame that shows reviews from users who are apart of the Vine Program.
  5. Created an unpaid DataFrame that shows reviews from users who are not apart of the Vine Program.
  6. Analyzed the percentage of 5 star reviews from both the paid and unpaid DataFrames.

## Resources
### Tools/Language
- PySpark spark-3.0.3
- Google CoLab
- PgAdmin 4 Version 6.1
- PostgreSQL 12.10-R1 
- AWS

### Sites/Data
- https://www.amazon.com/vine/about (Amazon Vine)

- https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt (datasets to choose from)

- https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Jewelry_v1_00.tsv.gz (jewelry dataset)

- https://data-hacks.com/convert-pyspark-dataframe-column-from-string-to-int-type-python (fixed error received while loading vine_df, converted star_rating column from string to integer)


## Results

### Vine Reviews

#### Total Number of Reviews

![Getting Started](images/total_paid.png)

#### 5 Star Reviews

![Getting Started](images/five_paid.png)

#### Percentage of Five Star Reviews

![Getting Started](images/per_paid.png)

### Non-Vine Reviews

#### Total Number of Reviews

![Getting Started](images/total_unpaid.png)

#### 5 Star Reviews

![Getting Started](images/five_unpaid.png)

#### Percentage of Five Star Reviews

![Getting Started](images/per_unpaid.png)

## Summary
- There was a least 7000 more total reviews for the unpaid members.
- Given that only 52% of the paid jewelry reviews had a 5 star rating and the unpaid reviews had about 58%, I cannot conclude that there is a positivity bias for reviewers apart of the Vine program.  
- I don't believe that there is enough paid reviews to determine bias because there was only a total of 21 reviews available for analysis.
- In the future, I would probably not filter for reviews that have at least 20 votes to increase the number of paid reviews to be analyzed.
