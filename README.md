# **Recipe Recommender Assignment EDA**

## **Problem Statement**
Step into the shoes of an ML engineer working at food.com. Your job is to design a recommender system to recommend recipes to users based on their choice and the current recipe they are looking at. 

The recommendation engine is a way to increase the website's user engagement. If a user is shown relevant recipes, they are more likely to spend more time on your site reading about recipes. Higher user engagement will likely result in more business opportunities like collaborations, promotions, etc.

The performance of a recommendation engine will significantly impact the revenue your recipe site can generate. 

Designing a recommender from scratch is a time-consuming task.  In this assignment, you are expected to explore the data and create features that will be used to build the recommender. 

## **Data**
You will be working with the two CSV files linked below. 

**_#raw recipe data_**
_s3a://raw-recipes-clean-upgrad/RAW_recipes_cleaned.csv_

**_#raw ratings data_**
_s3a://raw-interactions-upgrad/RAW_interactions_cleaned.csv_


The first file is the Raw_recipes.csv file. It contains all the recipe-related information. Each row in this file describes a recipe. 


The second file we will be using is the RAW_interactions.csv. Each row in this data file is one user reviewing one recipe. One user can review more than one recipe, and each recipe can be reviewed by more than one user, so there is a many-to-many relationship between users and recipes, but the combination of user_id and reviewer_id in each row will be unique. 


## **Feature Extraction Strategy**
As mentioned in the earlier segment, this part of the assignment is focused on extracting features from the data to build a recipe recommender system. 

Recall projects you have done so far. You have approached EDA with an objective in mind and focused your attention on extracting only the features you think might help with the end goal. At this point, we would like to introduce the concept of structured EDA. 

If you combine both data files, you will end up with the following features: 

minutes 
submitted
tags 
nutrition 
n_steps 
steps 
description
ingredients
n_ingredients 
date
rating
review


The first approach to EDA is to cover all possibilities for all columns. For instance, consider the submitted column. It has the date on which the user submitted a given recipe. 


You can use the current date to find the time duration that the recipe has been on your site. 
You can also check if there is any correlation between the time period on the website and the average ratings a recipe gets. 
If you subtract the submitted date from the review date, you will get a feature to measure the recipe's newness at the moment a user reviews it.
These are just a few possibilities. Once you have all the possibilities you want to explore, use your domain knowledge to prioritize. Keep the features you think will help decide the rating of a recipe. 


The second approach is project-specific. Focus on creating features that will help the model you are building. In this case, we will want to create features that capture the specifics of a recipe and user preferences. Imagine a hypothetical user who has rated a few dessert recipes highly. This user will likely rate other dessert recipes highly. You need to think of ways to capture both user preferences (this user likes deserts) and recipe details (this recipe is a dessert); they will add a lot of value to your model.  


we have the names of fields available in the data. Against each field, you can add the processing you intend to do and the features you intend to extract. Then, based on how valuable and time-consuming each exercise you listed is, you can prioritize processing a few features over others. For example, the tags field is a collection of stings. It will have tags that some users prefer over others. Processing the tags column will add a lot of value to your recommender system, so it gets the highest priority. 

 
On the other hand, consider the description column. The techniques needed to process the column are not known yet. Additionally, the tags column will already have some of the information you intend to extract from the description, so the description column will get a lower priority in this exercise. 
