---
layout: post
title: Tableau Showcase 1 - Price Tracking dashboard
subtitle: Monitor average price, price trend and price index
background: '/img/posts/soft_drink_shelf.jpg'
tags:
    - Tableau

---

# Background: Why do we need to track price?

After adapting to the new normal lifestyle, online shopping has become a dominant distribution method. With more retailers deploying their visual stores, online shoppers will spend extra effort to compare prices and product range. Retailers must monitor their competitors' moves and act correspondently.   

# Key Feature: What are we monitoring?
This dashboard focuses on three key matrixes: base and promo prices, price trend and the price index.

## Base and Promotional prices
Seasonal promotions are regularly seen in FMCG, therefore it's critical to track not only the regular prices but also the promotional prices. Also, the markdown percentage is shown in the table.

## Price Trend
This graph shows the price trends for average regular prices and average promotional prices in different retailers.

## Price Index
The price index is calculated with the following formula. This is useful to check which retailer has lower prices and by much percentage. 

<img src="/img/posts/tableau_showcase_1_formula.jpg" align="center" border="0" alt="Price\ Index = ( \frac{retailer\ price\ _1}{retailer\ price\ _2})" width="269" height="47" />

# Process of building this dashboard
The data is collected once a week. For each retailer, we need the product name, product ID and prices. Note if the product is in promotion, the base price (non-promotional) will be kept the same as last period. Also, we need a mapping table to map products from both retailers.  

# Example Insight
For the 600mL Spirit Bottle, the average base price in retailer 1 is $0.01 cheaper than retailer 2. But retailer 2 has a higher markdown percentage on average.

Taking a closer look, retailer 2 has a lower promotional price on average before Sep 12. After Sep 12, there is a large markdown in retailer 2 while retailer 1 slightly raised the promotional price.

<a href="/img/posts/tableau_showcase_1_insight_1.jpg" target="_blank">
<img src="/img/posts/tableau_showcase_1_insight_1.jpg" style="max-width:100%;" alt="Promotion Price Trend for 600mL Spirite in retailer 1">
</a>
*Promotion Price Trend for 600mL Spirite in retailer 1 (Click to see the enlarged picture).*
<br>

<a href="/img/posts/tableau_showcase_1_insight_2.jpg" target="_blank">
<img src="/img/posts/tableau_showcase_1_insight_2.jpg" style="max-width:100%;" alt="Promotion Price Trend for 600mL Spirite in retailer 2">
</a>
*Promotion Price Trend for 600mL Spirite in retailer 2 (Click to see the enlarged picture).*

# See it on Tableau Gallery [*Here*](https://public.tableau.com/views/ShopGrok_Test_YL_20200712/Products?:language=en&:display_count=y&:origin=viz_share_link)

By clicking at a product in the product table, graphs in the price trend and price index table will be updated.

<a href="https://public.tableau.com/views/ShopGrok_Test_YL_20200712/Products?:language=en&:display_count=y&:origin=viz_share_lin" target="_blank">
<img src="/img/posts/tableau_showcase_1_insight_3.jpg" style="max-width:100%;" alt="Price Variation Dashboard">
</a>
*Snapshot of the price variation dashboard (click to see the dashboard on Tableau Gallery).*
