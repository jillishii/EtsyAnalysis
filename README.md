# Project Problem and Hypothesis

## Problem
Etsy is a marketplace where creative entrepreneurs sell what they make or curate to online shoppers. There are 1.6 million active sellers with more than 35 million hand crafted items for sale. For the craftsman who is new to selling, how will they know which items will be most successful amid such a large marketplace? What are people actually buying?

## Hypothesis
Item reviews, categories and number of views will predict a (binary) outcome of whether or not an item will sell for a given item category on Etsy based on data obtained through scraping Etsy’s web pages. 


Alternate Hypothesis: Item reviews, categories and number of views will predict the (continuous probability) likelihood of an item sale for a given item category on Etsy and a given time period based on data obtained through scraping Etsy’s web pages. 

Alternate Hypothesis: Item reviews, categories and number of views will predict a (continuous quantitative) volume of sales for a given item category on Etsy and a given time period based on data obtained through scraping Etsy’s web pages. 

## Impact
A successful model which could be used to predict item sales would help Etsy sellers determine which products to focus on. Unlike marketing plans which serve only to increase viewership of the shop page, this model could potentially increase sales by predicting which items people desire. The predictor most likely to be of greatest value in this project will be the Review Date.

# Datasets
Data is obtained through HTML web scraping. Relevant predictors for my model include:

Variable | Description | Type
--- | --- | ---
Shop Name | Name of the seller's shop | qualitative
Shop Category | Category of items a shop sells | categorical
Review Item Title | Descriptive title of a sold item review | qualitative
Review Date | Date a sold item has been reviewed | discrete
Review Star Rating | 1 - 5 star rating of a sold item | discrete
Active Listing Titles | Descriptive title of an item for sale | qualitative
Active Listing Categories | Catefory of items a shop sells | categorical
Active Listing Views | Number of clicks or views an item on an item for sale | quantitative

# Domain knowledge
I have been an Etsy seller (and buyer) since 2010. There are many resources provided by Etsy through blogs and forums to help guide sellers to success. However, these are largely tips and narratives written by other sellers who are simply describing what worked best for them. All of these tips and tricks are based on seller’s trial and error and address success more from a marketing perspective than the products themselves. My project will address the products themselves and whether it is likely to sell or not.

## Existing Efforts
There is a site craftcount.com which ranks Etsy shops by sales over a given duration. You can also choose to see rankings for specific countries or categories. This is a useful tool, however the website only ranks shops that have specifically signed up to appear in the rankings. This means that there are a large number of shops which are not accounted for at all. 

# Potential Methods and Models
* For predicting a binary outcome of sale or no sale: logistic regression
* For predicting the quantitative outcome of volume of sales: linear regression
* For the classification portion of determining which season or date range to expect sales: K Nearest Neighbors

# Project Concerns

## Assumptions
For the purposes of this project, I will assume the following from my data:
* Unavailable Data: For privacy reasons, Etsy does not share sales data publicly on their website nor through their developer API. The ideal model would include lots of sales data such as price sold, date sold, country sold to, etc. My model will use publicly available “Item Reviews” as the set of items one shop has sold.
* The date an item was reviewed is occurring during the same month the item was purchased. 
* One shop sells items primarily in one category and will be analyzed as a shop of one category only.

## Risks of the Model
There is a cost value to any false predictions given by the model. A false positive prediction by this model would predict that a given item will sell when in fact it likely will not sell. The cost of materials and time spent creating this item can then be assumed to be time and money wasted. A false negative prediction is perhaps more difficult to realize because it would be an item not created at all because it was predicted to be unpopular or unlikely to sell when in fact it would have been a good product. In this case, the cost of the unmade item can be thought of as lost revenue.

## Risks of the Data
Since I do not have the raw sales data provided by Etsy which would verify location and user information, there is a risk that some shop reviews have been either falsified or inflated by family, friends, or the shop owners themselves on another account. 

## Concerns and Questions
I have several hypothesis that would work with the data, and all would give sellers more or less the same information. Which is the best way to measure in my scenario (binary outcome, probability outcome, or quantitative outcome)?

# Outcomes
The outcome of my model will predict whether or not an item will sell after selecting an item category and target time of sale. My target audience, which is Etsy sellers, would be able to use my model to predict whether or not to produce a certain item, or perhaps whether to list it only during certain seasons. A successful model will accurately predict the sale of an item with an 80% accuracy. The data will be randomized and used as both the training set and the test set of data.

I expect the Review Date to provide the most important outcome on its own because it will give a sense of the seasonality of specific items which are selling. With only this feature I will be able to tell which items are selling within which dates.
As a corollary of this project, I expect that another interesting feature would be know not only which items are popular and selling, but how much competition any given seller would face within a particular category. This also would impact the likelihood of items selling.
