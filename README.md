# Market-Basket-Analysis
 The purpose of this project is to understand customer purchasing behavior and optimize product placement and promotions for increased sales and customer satisfaction.  ‍ 
 Market Basket Analysis
Level : Intermediate Level
‍

Purpose :
The purpose of this project is to understand customer purchasing behavior and optimize product placement and promotions for increased sales and customer satisfaction.

‍

‍What you'll learn :
Association rule mining
Market basket analysis techniques
Data preprocessing for transactional data
‍

‍Tools :
Python (with libraries like mlxtend, Pandas, and scikit-learn)

‍

Analysis Process:
1. Data Preprocessing and Transformation:

Prepare the transactional data, converting it into a suitable format for market basket analysis (e.g., a matrix of transactions and products).
Encode the data to binary format (0 or 1) indicating whether a product was purchased or not.
2. Market Basket Analysis:

Apply association rule mining techniques (e.g., Apriori algorithm) to discover patterns and relationships between products.
Identify frequent item sets and strong association rules that can inform product recommendations or placement strategies.
3. Recommendation System Implementation:

Build a recommendation system based on the insights from market basket analysis to suggest complementary or related products to customers.
Have you ever walked into a supermarket and realized that all the items that go together are placed nearby? Or that they are placed so far away that you end up buying other items that you did not intend to in the walk between? Well, this is not a mere coincidence or lack of organization. Infact, these arrangements were made based on the data generated from transactions performed by thousands of customers like you! This technique, called Market Basket Analysis, is often used by supermarkets to decide on item arrangement, combo discount offers, and many such lucrative schemes to increase their sales.

In this beginner-friendly no-math tutorial, we will explore one of the main processes of Market Basket Analysis: Association Rule Mining. Let’s begin!

The first step in Association Rule Mining is to Find Frequent Itemsets. Let’s understand this step with the help of an example.

Here is a list of 12 sales transactions.

Sales Transactions in a Super Market
Sales Transactions in a Super Market
As we can see, 6 items are being sold- Milk, Bread, Butter, Egg, Cookies, and Ketchup.

Introducing Support- the count of all the transactions having a particular item. For example, the item Milk is purchased in transactions 1, 2, 4, 6, 7, 8, 10, 11, and 12. Hence, the support of Milk is 9. Support can also be represented as a percentage- for example, support of Milk is 9/12 = 75%, where 12 is the total number of transactions. Simple, isn’t it?

Here is a consolidated list of items and their support:

Itemsets of Size 1
Iteration 1: Itemsets of Size 1
A new terminology has been introduced in the above image- Itemset. An itemset is basically a group of items. In the above image, the size of the itemset is 1 since it contains only 1 Item.

A simple analysis can also be made from the above itemsets- that some itemsets are more popular than others. However, what is the minimum support that defines popularity? That is defined by a person known as the Subject Matter Expert. The Subject Matter Expert is someone who has extensive business knowledge and experience.

Let’s suppose that the Subject Matter Expert has defined the minimum support to be 33%. Hence, the minimum support for an itemset to be called popular or Frequent is 33% of 12, which is 4. Here, 12 is the total number of transactions.

Having the minimum support defined, let’s see which of the above itemsets of size 1 are frequent.

Frequent Itemsets of Size 1
Iteration 1: Frequent Itemsets of Size 1
As we can see, out of 6 itemsets, only 4 have support more than the minimum defined, and hence can be called frequent.

Now that we have found out the frequent itemsets of size 1, let’s move on and find itemsets of size 2. To do this, we generate all possible combinations from the list of frequent itemsets of size 1.

Itemsets of Size 2
Iteration 2: Itemsets of Size 2
Having generated itemsets of size 2, let’s find out the frequent itemsets and discard the others for further analysis. To do this, we calculate the support for each itemset, by counting the number of transactions in which both the items have occurred together. Remember, the minimum support defined by the Subject Matter Expert was 33%, which is 4.

Frequent Itemsets of Size 2
Iteration 2: Frequent Itemsets of Size 2
As we can see, out of 6 itemsets, only 4 have support more than the minimum defined, and hence can be called frequent.

Now that we have found itemsets of size 2, let’s move on and find itemsets of size 3. To do this, we generate all possible combinations from the list of frequent itemsets of size 2.

Itemsets of Size 3
Iteration 3: Itemsets of Size 3
Having generated itemsets of size 3, let’s find out the frequent itemsets and discard the others for further analysis. To do this, we calculate the support for each itemset, by counting the number of transactions in which all the three items have occurred together. Remember, the minimum support defined by the Subject Matter Expert was 33%, which is 4.


Iteration 3: Frequent Itemsets of Size 3
As we can see, out of 3 itemsets, only 1 has support more than the minimum defined, and hence can be called frequent.

Now since we have only 1 itemset of size 3 having support more than the minimum defined, we cannot form itemsets of larger sizes. Hence, we move on to the next step in Association Rule Mining.

Itemset = a group of items.

Frequent Itemsets = itemsets that have more than the minimum defined support.

Support = the count of all the transactions having a particular item/ itemset.

Subject Matter Expert = a person who defines the minimum support for an itemset to be called frequent.

The next step in the process of Association Rule Mining is Generating Association Rules from the Frequent Itemsets. Let’s understand this with the help of the same example that we have previously discussed.

Here is the largest frequent itemset that we found as a result of our analysis in the previous step:


Frequent Itemsets of Size 3
Our interpretation from the above image is that the items Milk, Bread, and Butter are bought together 6 times out of 12. However, how do we determine the order of purchase? That is, does buying Bread and Butter imply that the person will also buy Milk? Or does buying Bread and Milk imply that the person will also buy Butter? To know this, we generate and analyze association rules.

From these itemsets, we have formed the following association rules:

Association Rules
Association Rules
The above image introduces us to three terminologies:

Association Rules: Association Rules are used to find relationships between itemsets. For example, the first association rule can be read as- “If a person buys milk and bread, then they will also buy butter”.
Antecedent: The antecedent is the itemset that comes in the ‘If’ part of the association rule. In the first association rule, the antecedent is Milk and Bread.
Consequent: The consequent is the itemset that comes in the ‘Then’ part of the association rule. In the first association rule, the consequent is Butter.
Association Rule: If Antecedent, Then Consequent

To generate association rules, we have tried out all possible combinations of antecedent and consequent. Having consolidated all the rules, how do we filter out the ones which we can claim with a solid proof?

Introducing Confidence- the support of the frequent itemset given the antecedent. For example, in the first association rule, the support of the frequent itemset {Milk, Bread, Butter} is 6, and the support of the antecedent {Milk, Bread} is 7. Hence, the confidence of the rule is 6/7 = 86%.

Similarly, we compute the confidence of all the association rules:

Confidence of Association Rules
Confidence of Association Rules
The confidence of an association rule can be read as- 86% of the customers who buy Milk and Bread also by Butter.

Having computed the confidence of each of the association rules, let’s go back to the Subject Matter Expert to know the minimum confidence needed to prove the relevance of our association rules.

Let’s suppose that the minimum confidence defined by the Subject Matter Expert is 80%. Based on this, here is a list of association rules which can be used for Market Basket Analysis:

Filtered Association Rules
Filtered Association Rules
Hence, the best association rules that resulted after our analysis are:

{Milk, Bread} => {Butter} [Support = 50%, Confidence = 86%]
Which can be read as, “If a customer buys Milk and Bread, then there is a probability of 86% that they will also buy Butter”.

2. {Butter, Milk} => {Bread} [Support = 50%, Confidence = 86%]

Which can be read as, “If a customer buys Butter and Milk, then there is a probability of 86% that they will also buy Bread”.

Having generated the association rules, we move on to the next step in Association Rule Mining.

Association Rules = used to find relationships between itemsets.

Antecedent = the ‘if’ part of an association rule.

Consequent = the ‘then’ part of an association rule.

Confidence = the support of the frequent itemset given the antecedent.

The next step in the process of Association Rule Mining is Studying the Relationship between the Antecedent and the Consequent. Let’s understand this with the help of the same example that we have previously discussed.

Here are the association rules that qualify the minimum thresholds of support and confidence:

Filtered Association Rules
Filtered Association Rules
Looking at these from a sales perspective, does the increase in sales of either the antecedent or consequent imply the increase in sales of the other? That is, if the sales of Butter goes up, do the sales of Milk and Bread also go up? Or is it vice-versa? Or is the result a fluke?

Introducing Lift- the confidence of the association rule, given the consequent. For example, in the first association rule, the confidence of the rule ({Milk, Bread} => {Butter}) is 86% or 6/7, and the support of the consequent {Butter} is 83% or 10/12 . Therefore, the lift of the rule is (6/7)/(10/12) = 1.03.

Similarly, we compute the lift of the second rule:


Lift of Association Rules
Having calculated the lift values, let’s interpret these values. No, we won’t go back and bug the Subject Matter Expert again, because these results are common for all situations.

Lift < 1: the occurrence of the antecedent is negatively correlated with the occurrence of the consequent.
Lift > 1: the occurrence of the antecedent is positively correlated with the occurrence of the consequent.
Lift = 1: the occurrence of the antecedent is not correlated with the occurrence of the consequent, and the rule may be a fluke.
Hence, applying this to our association rules:

The first rule has a lift value more than 1, hence, the occurrence of the itemset {Milk, Bread} is positively correlated with the occurrence of {Butter}, or, if the sales of Milk and Bread increases, then the sales of Butter increases and vice-versa. Also, the result is not a fluke.
The second rule has a lift value of less than 1, hence, the occurrence of the itemset {Bread, Butter} is negatively correlated with the occurrence of {Milk}, or, if the sales of Bread and Butter increases, then the sales of Milk decreases and vice-versa. Also, the result is not a fluke.
Lift = the confidence of the association rule, given the consequent.![noi](https://github.com/user-attachments/assets/4f549414-320d-4fb6-9e2f-3e499870e378)
![niu](https://github.com/user-attachments/assets/8f1bdfec-9f61-4484-a9af-f5918c5899f1)
![market](https://github.com/user-attachments/assets/980cdc39-e06b-4eb9-ad02-1dc15a601ed3)
![lolpoi](https://github.com/user-attachments/assets/aedb320c-1c50-451a-b88f-27387d959639)
![lol](https://github.com/user-attachments/assets/588bd8f0-3137-46e4-82a1-3b40026c0722)
![klo](https://github.com/user-attachments/assets/3a1056ab-867f-4a4f-bed8-d51bafb57ef3)
![kio](https://github.com/user-attachments/assets/293f4d88-4ef2-4d30-ba25-40a87ccbd17b)
![data](https://github.com/user-attachments/assets/d170880c-16b1-40d6-9cfb-b47a6978c2ef)
![basket](https://github.com/user-attachments/assets/86d5b974-0950-44c0-b0cf-d44010a93cd5)

