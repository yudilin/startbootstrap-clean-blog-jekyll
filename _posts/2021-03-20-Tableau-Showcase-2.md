---
layout: post
title: Tableau Showcase 2 - Promotion Product Analysis Dashboard
subtitle: Find products that are attracting traffic, making profits or neither
background: '/img/posts/promotion_shopping_cart.jpg'
tags:
    - Tableau

---
*Photo by Karolina Grabowska from Pexels*

# Background: Why do we need to evaluate promotion products?
Clicking, searching, and switching tabs to compare prices have become one of the most common sets of actions while many of us shopped almost everything online. Retailers noticed this pattern and spent so much effort in providing better prices and product selection than their competitors to attract customers. 

After a sales promotion, it's critical to review what product generate profits or attract views. This dashboard tries to evaluate the effectiveness of the campaign and identify the winning and losing items. 

# Key Feature and Example Insight
This dashboard provides the following feature: compare the total revenue and profit from all items, compare product profit and residual profit from the related transaction. 

## Total Revenue and Total Profit
The size of the bubble represents the total revenue from this item relative to others. And the colour range from orange to blue states where the item profit falls.

<a href="/img/posts/tableau_showcase_2_insight_1.jpg" target="_blank">
<img src="/img/posts/tableau_showcase_2_insight_1.jpg" style="max-width:100%;" alt="Product Profit Bubble Chart">
</a>
<p style="text-align:center" ><i>Product Profit Bubble Chart and Table (Click to see the enlarged picture).</i></p>

In this bubble chart, we can see the visual pattern between revenue and profitability. Most of the products are making marginal revenue and profits, while some items are making significant profit and loss. 

For the solid orange bubbles, their size is larger than those in solid blue. This means the average revenue from the profit losing ones is more than the average revenue from profiting ones. They have fewer in numbers and are likely to be heavily discounted to attract traffic and customers. 

## Product Profit and Residual Transaction Profit.
Before we dive into the graph, we need to explain the concept of residual transaction profit and product profit. For the products we are analysing, we separate the profit of the product from the profit of the related transactions. In this way, we can see if this product is adding or losing profit in an order. 

<a href="/img/posts/tableau_showcase_2_insight_2.jpg" target="_blank">
<img src="/img/posts/tableau_showcase_2_insight_2.jpg" style="max-width:100%;" alt="Product Profit vs Residual Transaction Profit">
</a>
<p style="text-align:center" ><i>Product Profit vs Residual Transaction Profit Plot (Click to see the enlarged picture).</i></p>

The graph is divided into four quadrants. 
1. The most adored products are those fall into the first quadrant. This quadrant contains products that are generating profits as well as the rest of the order. 
2. The products in the second quadrant are those taking deep discounts while the rest of the order is gaining profit. Some of them might be catalogue products, they are generally losing profits but aim to attract customers to place orders alongside other profiting products. 
3. There are no products in the third quadrant, where the product and the rest of the order are losing profits. 
4. The products in the fourth quadrant are exactly the opposite of those in the second quadrant. Their profit is positive, while the rest of the order is negative. 

# Process of Building This Dashboard
Although the data for this example comes clean, the actual data in a similar situation is likely to come from at least two different tables: the order table, which shows all the product and sales prices; and the product procurement table, which contains the cost of all products. Then we can aggregate the profit from each SKU and the related transaction.  

# Further Exploration 
This analysis made a few assumptions. 
1. Consumers place transaction based on sales promotion. 
2. The promotion aims to generate profits. Thus, no discount is designed to reduce inventory level.

Assumption 1 can't explain all the consumers' behaviours. Some customers might initially want to buy the products without discounts. Then the promotional effect from the discounted products is exaggerated. We can only distinguish which discounted products don't work. 

We can also take a closer look at the products and customers. We can examine which product works well in this promotion and if they are from the same category or have any patterns. To better compare the result, we should compare the sales before and after the promotion. 

# See it on Tableau Gallery [*Here*](https://public.tableau.com/views/Chap4_Product_Profitability/ProductProfitabilityDashboard?:language=en&:display_count=y&:origin=viz_share_link)


<a href="https://public.tableau.com/views/Chap4_Product_Profitability/ProductProfitabilityDashboard?:language=en&:display_count=y&:origin=viz_share_link" target="_blank">
<img src="/img/posts/tableau_showcase_2_dashboard.jpg" style="max-width:100%;" alt="Price Variation Dashboard">
</a>
*Snapshot of the product profitability dashboard (click to see the dashboard on Tableau Gallery).*

