# Amazon_Vine_Analysis

## Overview

Since my work with Jennifer on the SellBy project was so successful, I’ve been tasked with another, larger project: analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, I’ll have access to approximately 50 datasets. Each one contains reviews of a specific product, from clothing apparel to wireless products. I’ll need to pick one of these datasets and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, I’ll use PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in your dataset. Then, I’ll write a summary of the analysis for Jennifer to submit to the SellBy stakeholders.

Of the 50 datasets, I chose to analyze reviews that were made by users in the **"Electronics"** category. 

 - Dataset used for this analysis can be found [here](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Electronics_v1_00.tsv.gz)

## Results

Over 3 million reviews were captured in the dataset. We needed to filter the dataset so that we could focus on reviews that were more likely to be useful.

 - Count of Total Votes equal or greater than 20. 
 - Percent of Helpful Votes to Total Votes equal or greater than 50%. 

The total number of reviews was lowered from 3 million to 50.7 thousand as a result of the findings. As a result, we were able to answer the following questions:

### 1. How many Vine reviews and non-Vine reviews were there?

 - Only 2.1 percent (1,080) of the reviews were from **Vine** members, while the rest 97.9% were from **Non-Vine** members (49,659).

### 2. How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?**

 - Members of **Vine** awarded 454 out of 1,080 reviews a five-star rating.
 - Non-Vine members rated 23,034 of the 49,659 reviews as 5 stars.

### 3. What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

 - **Vine** members received 42 percent of five-star reviews.
 - **Non-Vine** members received 46.4 percent of the 5-star reviews.

## Summary

The data reveal that **Vine** members were not biased when evaluating their items, despite the fact that the number of 5-star ratings was around 10% lower than **Non-Vine** members (42 percent vs. 46.4 percent ). As a result, we may suppose Vine consumers are more critical when writing reviews. However, rather than restricting the data to a proportion of helpful vs. total votes as we did for this research, we should include all of the data to further support this claim. Examining the data as is would provide us with more information and allow us to strengthen our hypothesis, as illustrated below.

Furthermore, repeating the research with datasets from multiple product categories can provide us a complete picture of whether or not reviews written by **Vine** members are biased.