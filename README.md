# Amazon Vine Analysis

## Project Overview

The motivation behind this project is to analyze Amazon reviews written by members of the paid Amazon Vine program. This service allows manufacturers and publishers to receive reviews for their products. Companies pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. The primary question we seek to answer: is there any positivity bias for reviews in the Vine program?

I was provided access to approximately 50 datasets and was instructed to pick one to perform the ETL process on. I selected the product category of Mobile Electronics (with reviews from the United States Marketplace).

## Resources
* PySpark
* Hadoop
* Postgresql
* PGAdmin
* Google Colab
* AWS – specifically RDS and S3 
* Data Sources: .sql, .ipynb, and .tsv files

## Results

Overall, the ETL process was smooth, and was performed without any significant issues. I did hit a bit of a speed bump when reviewing the Deliverable 2 instructions as it wasn’t entirely clear which DataFrames should be used in the calculations outlined in step 5. To make certain I did not miss an opportunity to uncover important insights, I performed additional calculations to feel confident in my findings. 

In an attempt to keep the analysis succinct, I will only speak to a single set of calculations below. You can view the entire code [here](https://github.com/Kelfang/Amazon_Vine_Analysis/blob/main/Vine_Review_Analysis.ipynb).  

To answer the primary question of this analysis, we need to address three questions regarding this data, specifically the Mobile Electronics category, and I will outline those below. 


----------------------------------------------------------------------
    1.	How many Vine reviews and non-Vine reviews were there?
    
<sub>Total Review Count</sub>

![review_count_20_plus_votes](https://github.com/Kelfang/Amazon_Vine_Analysis/blob/main/images/review_count_20_plus_votes.png)


<sub>Count – Vine Reviews</sub>

![paid_vine_reviews_count](https://github.com/Kelfang/Amazon_Vine_Analysis/blob/main/images/paid_vine_reviews_count.png)


<sub>Count – Non-Vine Reviews</sub>

![unpaid_vine_reviews_count](https://github.com/Kelfang/Amazon_Vine_Analysis/blob/main/images/unpaid_vine_reviews_count.png)

As you can see in the images above, there are 1,190 reviews that have a total vote count of 20 or more. An additional filter was applied to account for the reviews that had the helpful votes equal or exceed 50%. That left us with a total of four Vine reviews. The total for non-Vine reviews is far more at 1,064.

----------------------------------------------------------------------
    2.	How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

<sub>Vine 5-Star Reviews</sub>

![vine_five_star_reviews](https://github.com/Kelfang/Amazon_Vine_Analysis/blob/main/images/vine_five_star_reviews.png)


<sub>Non-Vine 5-Star Reviews</sub>

![non_vine_five_star_reviews](https://github.com/Kelfang/Amazon_Vine_Analysis/blob/main/images/non_vine_five_star_reviews.png)

When the 5-star rating filter is applied, you can see the numbers drop. This is absolutely the case with the Vine reviews as the number drops to one. On the other hand, the non-Vine 5-star rating sits at a much higher number of 557.


----------------------------------------------------------------------
    3.	What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

<sub>Vine 5-Star Reviews Percentage</sub>

![vine_five_star_percentage](https://github.com/Kelfang/Amazon_Vine_Analysis/blob/main/images/vine_five_star_percentage.png)


<sub>Non-Vine 5-Star Reviews Percentage</sub>

![non_vine_five_star_percentage](https://github.com/Kelfang/Amazon_Vine_Analysis/blob/main/images/non_vine_five_star_percentage.png)

The percentages reflect the count of the reviews outlined in the second questions. The Vine program five-star reviews are less than 1% at 0.18%. Which means that the non-Vine program five-star reviews are much higher at 99.82%.


----------------------------------------------------------------------

## Summary 

Based on my findings within this dataset, I can ***cautiously*** state that there appears to be no positivity bias for reviews on the Mobile Electronics category in the Vine program. The cause of my hesitation is based purely on the low number of Vine reviews that met the filtered criteria. I did confirm my statement by running two sets of calculations on the data (shown in my code [here](https://github.com/Kelfang/Amazon_Vine_Analysis/blob/main/Vine_Review_Analysis.ipynb)). 

The first set is the single filter of reviews that have 20 (or more) total votes. The second set runs an additional filter that narrows the focus to reviews that have helpful votes that equal or exceed 50%.  I found that both sets of calculations are nearly identical, with percentages being separated by 0.01%.  

Another avenue would be to remove all filters and run the calculations again to determine if my findings are valid. I would also like to perform the same ETL process on other datasets from the list provided to get a better understanding of the entire program, instead of dissecting a singular category. There could be some variability among the categories, volume of reviews, and dollar value of the item gifted in exchange for a review. 

