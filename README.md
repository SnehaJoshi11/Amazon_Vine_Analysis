# Amazon_Vine_Analysis

## Project Overview

To Analyze Amazon reviews written by members of the paid Amazon Vine program. In this project, we will have access to approximately 50 datasets. Each one contains reviews of a specific product, from clothing apparel to wireless products.


## Purpose

In this project we need to pick one of the datasets from [Amazon reviews](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt) and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, we must use PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in your dataset. Then, write a summary of the analysis to submit to the SellBy stakeholders.

## Background - Amazon Vine


- The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.
- The products are then passed to Amazon reviewers who are then required to publish a review.
- Past and present participating companies include Logitech, Harper Collins, Philips, Samsung, Bose, Sony, Tefal, Microsoft, Breville, Bosch, Garmin, Dyson, Remington, Case Logic, Creative, Braun, Sennheiser, Olympus, LG, Black & Decker, Acer, and Walker.
- Books Reception for the program has been mixed with some people criticizing the program's use of non-professional reviewers while others cited this as a benefit.
- The Vine program operates independently on Amazon.com, Amazon.co.uk,Amazon.fr, Amazon.de, Amazon.ca, and Amazon.es. [Source: Wikipedia](https://en.wikipedia.org/wiki/Amazon_Vine) 



## Requirement
- Perform ETL on Amazon Product Reviews
- Determine Bias of Vine Reviews
- Summary Analysis

## Resources
Data Source

-	[Amazon Vine Reviews for grocery items](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Grocery_v1_00.tsv.gz)

Software:

-	Google Colab [Vine_Review_Analysis.ipynb](Vine_Review_Analysis.ipynb)
-	PgAdmin
-	AWS [Amazon_Reviews_ETL.ipynb](Amazon_Reviews_ETL.ipynb)

Languages:

-	pySpark

Note: Password from Amazon_Reviews_ETL.ipynb file is deleted for safety reason. File needs pgAdmin password in order to run.
## Results
In this analysis we analyzed reviews that have more than 20 total votes and the percentage of helpful votes is equal or greater than 50.

***How many Vine reviews and non-Vine reviews were there?***

There were
- **61 Vine** reviews and 
- **28287 non-Vine** reviews.

<p align="center">
<img src="Images/Total_Reviews(vine-nonvine).png" width="50%" height="50%">
</p>

<p align="center">
<i>Figure 1: Total Vine and non-Vine reviews.</i>
</p>


***How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?***

There were
- **20** five stars **Vine** reviews and 
- **15689**  five stars **non-Vine** reviews.

<p align="center">
<img src="Images/5Star_Reviews(vine-nonvine).png" width="50%" height="50%">
</p>

<p align="center">
<i>Figure 2: 5-star Vine and non-Vine reviews.</i>
</p>

***What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?***

- **32.79 %** of **Vine** reviews were 5 stars and 
- **55.46 %** of **non-Vine** reviews were 5 stars.

<p align="center">
<img src="Images/5Star_Review_Percentage(vine-nonvine).png" width="50%" height="50%">
</p>

<p align="center">
<i>Figure 3: Percentage of 5-star Vine and non-Vine reviews.</i>
</p>


## Summary

The purpose of this analysis is to analyze and determine if there is any bias toward favorable reviews from Vine members in the dataset. We can analyze reviews that have more than 20 total votes and the percentage of helpful votes is equal or greater than 50. This selection was made to pick reviews that are more likely to be helpful.

**Positivity bias for reviews in the Vine program**

In the analysis 5-star reviews within conditions mentioned above. Calculations show that there is **no positivity bias for reviews in the Vine program**. The results show that percentage of 5 stars Vine reviews is 32.79% and percentage of 5 stars non-Vine reviews is 55.46%. **Non-Vine reviews** have **higher percentage** of the 5 stars reviews.

**Additional analyses and suggestions**

We could expand this analysis by calculating percentage for all-star’s reviews. Based on the results (Figure 4), there is a larger difference in percentage for 1-star reviews than for 5-stars reviews. Vine reviews have **11.47% of 1-star reviews**, while non-Vine reviews have **22.67 % 1-star reviews** within conditions mentioned above. Similarly, there is **9.84% 2-stars Vine reviews** and **5.85% 2-stars non-Vine reviews**.  
<p align="center">
<img src="Images/Allstars_Percentage_Review(vine-nonvine).png" width="70%" height="70%">
</p>

<p align="center">
<i>Figure 4: Summary table for all-star reviews.</i>
</p>

The results show that there could be positivity bias for reviews in the Vine program, as per the 1 and 2-star reviews perspective. 

- In this case Vine reviews won’t affect the overall rating of the items.
- On Amazon site for Vine reviews [https://www.amazon.com/gp/vine/help](https://www.amazon.com/gp/vine/help), It gives detailed information about it.
- Also, it will be fair enough to perform analysis on items that are similar (in one group with Vine reviews and the other without) to measure sales profit over the period.
- Based on that We can observe that this approach is beneficial to newly released items to increase their sales faster.



