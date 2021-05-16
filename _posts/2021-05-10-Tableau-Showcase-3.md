---
layout: post
title: Tableau Showcase 3 - Customer Cluster Dashboard
subtitle: Know your customers better
background: '/img/posts/shibuya_crossing.jpg'
tags:
    - Tableau

---
*Photo by Tony Wu Photography 🇲🇲 from Pexels*

# Background: Why do we need to put customers into different groups?
“You may also like... Customers who viewed this item also viewed...". Whenever we scroll down the shopping page, there is always a section that suggests products you may like. Instead of having a shopping assistant or related products display on the nearby shelves, this recommendation section introduces potential sales in online retail. Therefore it's critical to know what the customers are likely to purchase.  

# Key Feature and Example Insight
This dashboard first divides members into ten groups based on their transaction value, shopping categories and frequency. After splitting these members into 10 clusters, I try to examine the characteristics of each group, such as which spend most in each transaction, which category they prefer to shop, and how often they shop. 

As mentioned above, the clusters are calculated based on total transaction value, average transaction value by categories and their shopping frequency. The clusters can be created on the analytics panel. Also, I transform the transaction value from dollar value to log10(transaction value) to keep all data on a smaller scale.

<a href="/img/posts/tableau_showcase_3_cluster.jpg" target="_blank">
<img href="/img/posts/tableau_showcase_3_cluster.jpg" target="_blank" src="/img/posts/tableau_showcase_3_cluster.jpg" style="max-width:50%; vertical-align:middle" alt="Cluster Section">
</a>
<p style="text-align:center" ><i>Cluster Section (Click to see the enlarged picture).</i></p>

## Customer Clustering by Total Value
From the transaction value distribution graph, we can see most of the transactions are under $1000. This low transaction value pattern matches our expectation since our store is an online supermarket, covering a full range of products.

<a href="/img/posts/tableau_showcase_3_insight_1.jpg" target="_blank">
<img src="/img/posts/tableau_showcase_3_insight_1.jpg" style="max-width:70%;vertical-align:middle" alt="Transaction Distribution">
</a>
<p style="text-align:center" ><i>Transaction Distribution (Click to see the enlarged picture).</i></p>

When we add the customer cluster and the reference line to the graph, we can see the total transaction for a few customer groups climb faster than the others. Customers from cluster 4, 5, 7, 9, 10 have higher transaction values than others. 

<a href="/img/posts/tableau_showcase_3_insight_2.jpg" target="_blank">
<img src="/img/posts/tableau_showcase_3_insight_2.jpg" style="max-width:70%;vertical-align:middle" alt="Sum of Transaction Value">
</a>
<p style="text-align:center" ><i>Sum of Transaction Value (Click to see the enlarged picture).</i></p>

## Customer Clustering by Average Transaction Value per Categories
As for the transaction value by categories graph, it shows the average transaction value in each category. It has revealed a different customers' behavioural pattern for us. The customers who paid for a higher transaction value order shopped less frequent than others. We can further dive into which categories of products they like to buy and target them precisely. For those customers from cluster 1, they are either new members or members that don't return.

<a href="/img/posts/tableau_showcase_3_insight_3.jpg" target="_blank">
<img src="/img/posts/tableau_showcase_3_insight_3.jpg" style="max-width:50%;vertical-align:middle" alt="Average Transaction Value by Category">
</a>
<p style="text-align:center" ><i>Average Transaction Value by Category (Click to see the enlarged picture).</i></p>

## Cluster Size and Total Transaction Value
This graph tells us that the higher spending customers, such as group 5,7, 9 and 10 make up a small fraction of overall customers. Customers from group 4 is a special case, this cluster has the 2nd largest customers base among all groups while still being at the high spending level.  

<a href="/img/posts/tableau_showcase_3_insight_4.jpg" target="_blank">
<img src="/img/posts/tableau_showcase_3_insight_4.jpg" style="max-width:70%;vertical-align:middle" alt="Cluster Size and Total Value">
</a>
<p style="text-align:center" ><i>Cluster Size and Total Value (Click to see the enlarged picture).</i></p>

## Total Transaction Value and Frequency by Product Categories
From 
This graph gives us more details about what categories do a cluster prefer to buy.

Here are some observations based on the graph:
Food and snacks categories take up the majorities of values and frequencies in almost all groups.
Group 1, 2, 3, 6 and 8 spend a significant amount of money on food and snack categories. While group 1 has the most members, and group 3 has the second to largest transaction value. 
Group 4 has the highest spending among all, they tend to buy cosmetics, electronics, sportswear and clothing. This shopping pattern seems to be a family.
Similar to group 4, group 5 purchased in the same categories but with a transaction amount.
Group 9 made no significant purchase than home appliances. Group 7 purchase cell phones besides home appliances. 
Group 10 is the minority group, they don't have sufficient data to reveal patterns. 
<a href="/img/posts/tableau_showcase_3_insight_5.jpg" target="_blank">
<img src="/img/posts/tableau_showcase_3_insight_5.jpg" style="max-width:100%;vertical-align:middle" alt="Transaction Value and Frequency by Categories">
</a>
<p style="text-align:center" ><i>Transaction Value and Frequency by Categories (Click to see the enlarged picture).</i></p>

# Process of Building This Dashboard
Besides the usual procedures such as removing duplicates, null values. There are some transactions recorded with negative values. Although they might have some business meaning, for analysing here we remove these negative values. 

# Further Exploration 
This customer clustering only considers the content based on their transaction: value, product categories and frequency. Combining the customers' acquisition time, channel, personal profile and location, we can better explain each group of customers.

# See it on Tableau Gallery [*Here*](https://public.tableau.com/views/CustomerClusteringDashboard/CustomerClusterbyProductCategories?:language=en&:display_count=y&:origin=viz_share_link)


<a href="https://public.tableau.com/views/CustomerClusteringDashboard/CustomerClusterbyProductCategories?:language=en&:display_count=y&:origin=viz_share_link" target="_blank">
<img src="/img/posts/tableau_showcase_3_dashboard.jpg" style="max-width:100%;vertical-align:middle" alt="Customer Clustering Dashboard">
</a>
*Snapshot of the Customer Clustering Dashboard (Click to See the Dashboard on Tableau Gallery).*
