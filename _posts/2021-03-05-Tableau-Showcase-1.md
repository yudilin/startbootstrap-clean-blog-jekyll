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
Seasonal promotions are regularly seen in FMCG, therefore it's critical to track not only the regular prices but also the promotional prices. Also mark down percentage is also shown in the table.

## Price Trend
This graph shows the price trends for average regular prices and average promotional prices in different retailers.

## Price Index
The price index is calculated with the following formula. This is useful to check which retailer has lower prices and by much percentage. 

<img src="https://bit.ly/3qmRs6H" align="center" border="0" alt="Price\ Index = ( \frac{retailer\ price\ _1}{retailer\ price\ _2})" width="269" height="47" />

# Process of building this dashboard
The data is collected once a week. For each retailer, we need the product name, product ID and prices. Note if the product is in promotion, the base price (non-promotional) will be kept the same as last period. Also, we need a mapping table to map products from both retailers.  

# Example Insight
For the 600mL Spirite Bottle, the average base price in retailer 1 is $0.01 cheaper than retailer 2. But retailer 2 has a higher markdown percentage on average.

Taking a closer look, retailer 2 has a lower promotional price on average before Sep 12. After Sep 12, there is large markdown in retailer 2 while retailer 1 slightly raised the promotional price.
<img src="/img/posts/tableau_showcase_1_insight_1.jpg" alt="Promotion Price Trend for 600mL Spirite in retailer 1" width = "100%">
*Promotion Price Trend for 600mL Spirite in retailer 1*
<br>

<img src="/img/posts/tableau_showcase_1_insight_2.jpg" alt="Promotion Price Trend for 600mL Spirite in retailer 2" width = "100%" >
*Promotion Price Trend for 600mL Spirite in retailer 2*

# See it on Tableau Gallery [Price Variation Dashboard](https://public.tableau.com/views/ShopGrok_Test_YL_20200712/Products?:language=en&:display_count=y&:origin=viz_share_link)

By clicking at a product in the product table, graphs in the price trend and price index table will be updated.

<div class='tableauPlaceholder' id='viz1615038323467' style='position: relative'><noscript><a href='#'><img alt=' ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Sh&#47;ShopGrok_Test_YL_20200712&#47;Products&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='ShopGrok_Test_YL_20200712&#47;Products' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Sh&#47;ShopGrok_Test_YL_20200712&#47;Products&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1615038323467');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.width='1600px';vizElement.style.height='927px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='1600px';vizElement.style.height='927px';} else { vizElement.style.width='100%';vizElement.style.height='1277px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>