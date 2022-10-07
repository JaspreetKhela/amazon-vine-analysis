# Amazon Vine Analysis

## Overview of the Analysis
### Purpose
The purpose of this analysis was to analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. 

### ETL Process
A video games dataset was imported into AWS and PySpark was used to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, Pandas was used to determine if there was any bias towards favorable reviews from Vine members in the chosen product reviews dataset.

## Results
### pgAdmin Database Screenshots
_____

<img width="1440" alt="1_pgadmin" src="https://user-images.githubusercontent.com/80941606/194560534-0d509e3e-f465-465c-a9db-438fdbf27093.png">
<img width="1440" alt="2_pgadmin" src="https://user-images.githubusercontent.com/80941606/194560556-e9a617d3-eb51-4a98-92c0-ab55e77cd5bb.png">
<img width="1440" alt="3_pgadmin" src="https://user-images.githubusercontent.com/80941606/194560575-8a4ba46d-b7cf-4a9b-a6a3-9f9885f0f071.png">
<img width="1440" alt="4_pgadmin" src="https://user-images.githubusercontent.com/80941606/194560592-f4cdd49c-88d6-42c9-b210-6f6ff20adb7c.png">
<img width="1440" alt="5_pgadmin" src="https://user-images.githubusercontent.com/80941606/194564471-8553f3df-6b9b-4214-a49a-4c4708cffb81.png">

**Figure 1**: These images shows that the AWS database can be accessed and used to populated the local PostgreSQL database using pgAdmin.
_____

### Analysis
The vine_review_analysis.ipynb file performed an analysis on the video games reviews dataset that allows us to answer the following questions:
* How many Vine reviews and non-Vine reviews were there?
  * There were 94 Vine reviews and 40,471 non-Vine reviews.
* How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
  * There were 48 five-star Vine reviews and 15,663 five-star non-Vine reviews.
* What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
  * Roughly 51.06% of Vine reviews were five stars and roughly 38.70% of non-Vine reviews were five stars.

## Summary
### Bias
In summary, since roughly 51.06% of Vine video games reviews were five stars, which is much higher than 38.70% of non-Vine video games reviews that were five stars, we can conclude that the Vine reviewers had a positive product review bias. However, since there were significantly fewer Vine reviewers than non-Vine reviewers, we cannot definitively conclude that Vine reviewers in general write more positive product reviews than non-Vine reviewers do; consequently, more Vine product review data is needed to arrive at a definitive conclusion.

### Additional Analysis
For additional analysis, we can perform the same analysis using other datasets and then compare the percentages of positive product reviews written by Vine reviewers against those of positive product reviews written by non-Vine reviewers. Moreover, we can also adjust the DataFrame filter arguments used in the vine_review_analysis.ipynb file to include a broader set of records in a chosen product reviews dataset.
