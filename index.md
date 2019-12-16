---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
title: Applied Dunnhumby Analysis
bigimg: /img/banner.jpg
---

# Introduction

This project aims to explore how people consume goods and what might influence the purchase of these goods. For that purpose, The Complete Journey dataset from Dunnhumby was used. It provides various information about transactions from 2’500 households at a retailer over two years (content of their baskets, use of coupons, household’s information, etc.).
Having access to these information offers interesting perspectives, such as:
*	Which goods are the most purchased and which are the least purchased?
*	What goods are frequently or rarely bought together?
*	Do the income and/or the number of children have an influence on the purchases?


# First section

First, we focused on finding which types of good (commodities) are the most purchased. We used the content of the baskets to find which products appeared the most. The most purchased products are presented in the following plot:

![plot2](img/plot2.png)

One would expect that products which are purchased in the higher number of baskets are cheap and basic goods. We can see that, indeed, the top 5 contains soft drinks, dairy products, bread, snacks and cheese.

However, we see that the most common bought commodity was found in only 6% of the baskets.
This result informed us that no products are systematically dominant, and it is a good indication of the variety of the purchases, and therefore we have a nice environment to study relationships between products. 

For this purpose, we first created a graph in which each node represents a product, and by clicking on one node/product, we can visualize which products were purchased at least once with this particular product. 
{% include interactive_graphs.html  %}

Another important visualization of these relationships might be obtained by studying the co-purchase matrix of the products, and see if patterns or correlations can be observed. Note that the above graph illustrates the relationships present in the co-occurence matrix, but does not take into account the number of times two products have been bought together. Therefore, this additional visualization allow us to get different information, by expliciting the number of products bought with a particular product, and the number of times it has been the case.

![plot3](img/plot3.png)

As we can see on the above co-purchase matrix, some products are always bought alone, whereas some others are bought with a lot of other products (these should be the above most purchased products among all baskets). Note that higher value of the co-occurence matrix does correspond to a higher number of co-purchase for two given products. 

Now, another interesting point to study is the identification of bridges among our products. A bridge basically is a pair of products that are exclusively bought together, without any other product. Bridges are an interesting component because they might represent links between distinct clusters of products (see more about that on the next paragraph), considering our product network. Furthermore, they offer an interesting economic insight in its own way. Here are the interesting bridges we identified in our product network: (product of the right is the only other product to which product of the left was linked)
*	FUEL -> CIGARETTES
*	ROSES -> GREETING CARDS/WRAP/PARTY SPLY
*	SANDWICHES -> SOFT DRINKS
*	CHIPS&SNACKS -> SOFT DRINKS
*	SYRUPS/TOPPINGS -> ICE CREAM/MILK/SHERBTS

As we can see, these bridges are quite intuitive. Now, a central aspect of the study of the product network is to identify groups or "clusters" of products, which are often bought together and form "communities" that are intuitive in the economical point of vue. After having tried to remove bridges to get these groups, we figured out that every bridge was only linking one particular product to a giant component. Therefore, we had to proceed with another tool to find groups. We got pretty interesting results using cliques, which aer groups of products in which all pairwise combinations have been purchased at least once together. Below, you will find an interactive plot in which you have the possibility to select some cliques and highlight them in the product network.

(interactive cliques plot here)

We can see in the examples presented above that Soft drinks and Fluid milk products appear in a lot of cliques. This is consistent with the first results where we observed that Soft drinks and Fluid milk products are the two most present products in the baskets.

This shows that some patterns can be observed. What could be some driving factors for these patterns ?
This will be the subject of the next section, where two potential factors were studied : the household’s income and the number of children.

# Second section

Let’s look at the relationship between the household’s income, the number of children, and the weekly expenditure for different commodities.

a)	Household’s income :

The three commodities most correlated with the income are Suntan, Home health care and Snack nuts. It was found that for Suntan products and Home health care products, the weekly expenditure increases as the household’s income increases. These types of products can be considered as luxury products and are expected to correlate with income. However, another interesting result we obtained was for Snack nuts products for which the same effect is observed. This might be more surprising, but it might be explained by the fact that they are usually more expensive than other snacks.

b)	Number of children :

The three commodities most correlated with the number of children are Convenient brkfst/whlsm snacks, Halloween and Glassware and dinnerware. As the number of children in the household increases, the weekly expenditure increases also.

The following plot shows the combination of both studied factors on the different commodities :

![correlations](img/correlations.png)

It appears plausible that we can detect groups or communities among products based on their relationships.
It could then be interesting to study the influence of income on purchases of these groups and obtain a more comprehensive understanding of consumption behavior.

# Third section

Add third section here
