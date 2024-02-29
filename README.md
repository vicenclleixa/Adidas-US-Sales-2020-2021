# Adidas 2020-2021 US Sales EDA insights
### Vicenç Lleixà (https://github.com/vicenclleixa)

![A Kroger worker](https://github.com/vicenclleixa/Adidas-US-Sales-2020-2021/blob/main/other%20images/Adidas%20Store.jpg?raw=true)

## Index:
##### 1.Data acquisition, formats and libraries:
##### 2.Exploratory analysis: insights, visualizations and conclusions
##### 2.1.Dataframe Review and Handling
##### 2.2.Sales and profits
##### 2.2.1.Seasonal revenue
##### 2.2.2.Revenue and Earnings by City
##### 2.2.3.Revenue and Earnings by Region
##### 2.2.4.Revenue and Earnings by State
##### 2.2.5.Sales and Profit Comparison: California vs. Florida
##### 2.2.6.Revenue and Earnings by Retailer
##### 2.2.7.Revenue and Earnings by Product

## 0.Introduction
##### In this Exploratory Data Analysis, we examine a staggering total of 899,902,125 Adidas sales that occurred in the United States of America during the years 2020 and 2021. 

##### We plan to explore essential questions, supported by relevant visual aids. Our study will include a careful comparison of sales volumes in different regions. An important part of our work will focus on uncovering sales and profit figures for each city, region, and state. Additionally, we will examine performance metrics across various states. An essential component of our analysis will also involve looking at how products are categorized and the profit margins associated with them. This comprehensive strategy will help us gain a deep and nuanced insight into the data we have.

##### This is a project that I have developed on my own. It is true that in the Master's program I am currently enrolled in, we engage in various exercises, but I am always seeking to improve my skills.

## 1.Data acquisition, formats and libraries:
##### The dataset, sourced from Kaggle in .xlsx format, comprises various columns, each representing a unique variable. Given that each column represents a distinct variable, the dataset is clearly well-organized and clean.
##### First things first we import the libraries necessary for our approach in this analysis: 
##### We will use pandas for its robust data manipulation and analysis capabilities, enabling us to easily handle and explore complex datasets through its intuitive DataFrame structures. 
##### Alongside pandas, we'll employ NumPy to perform efficient numerical computing, utilizing its powerful array objects and comprehensive mathematical functions for operations ranging from simple arithmetic to complex statistical analysis. 
##### For visual representation of our data, matplotlib.pyplot will be our go-to for creating a wide range of static, interactive, and animated visualizations, allowing us to convey our findings visually. Within the realm of plotting, matplotlib.ticker will provide us with the ability to customize tick locations and formats, enhancing the readability and professionalism of our graphs. In our Jupyter notebooks, the %matplotlib inline command will be indispensable for displaying these plots directly within the notebook, seamlessly integrating our visual analysis. 
##### To elevate our data visualization further, seaborn will be used for its statistical plotting capabilities, offering a higher-level interface that produces attractive and informative graphics with ease. 
##### Finally, for any geospatial data analysis, we'll turn to geopandas. This library extends pandas to allow for the manipulation and visualization of geospatial data, enabling us to incorporate geographic information into our analysis effectively.
##### Once we've imported the necessary libraries, our next step involves loading the dataset and making a copy of it. This approach ensures that we can work freely without the risk of altering the original data, safeguarding against any potential issues that might arise from modifications to the raw dataset.

## 2.Exploratory analysis: insights, visualizations and conclusions
### 2.1.Dataframe Review and Handling
##### The .xslx dataframe has 9648 rows and a total of 13 columns. These columns include 'Retailer', 'Retailer ID', 'Invoice Date', 'Region', 'State', 'City', 'Product', 'Price per Unit', 'Units Sold', 'Total Sales', 'Operating Profit', 'Operating Margin', and 'Sales Method'. All the values are object-type and there are no NaN values.
##### We will focus our analysis on sales data from a wide array of cities including New York, Houston, San Francisco, Los Angeles, Chicago, Dallas, Philadelphia, Las Vegas, Denver, Seattle, Miami, Minneapolis, Billings, Knoxville, Omaha, Birmingham, Portland, Anchorage, Honolulu, Orlando, Albany, Cheyenne, Richmond, Detroit, St. Louis, Salt Lake City, New Orleans, Boise, Phoenix, Albuquerque, Atlanta, Charleston, Charlotte, Columbus, Louisville, Jackson, Little Rock, Oklahoma City, Wichita, Sioux Falls, Fargo, Des Moines, Milwaukee, Indianapolis, Baltimore, Wilmington, Newark, Hartford, Providence, Boston, Burlington, and Manchester. 
##### Additionally, we will consider sales across various regions such as the Northeast, South, West, Midwest, and Southeast, as well as evaluate sales performance in the following states, ranked by their sales volumes: New York, California, Florida, Texas, South Carolina, Washington, North Carolina, Louisiana, Hawaii, Virginia, Oregon, Colorado, Nevada, New Mexico, Idaho, Georgia, Michigan, Wyoming, Ohio, and Tennessee. This comprehensive approach will give us a broad yet detailed view of sales trends across significant parts of the United States.
##### In our analysis, we also consider sales data from a select group of retailers, each known for their distinct market presence and customer base. The list includes West Gear, Foot Locker, Sports Direct, Kohl's, Amazon, and Walmart. These retailers play a crucial role in distributing our diverse product range, from Men's Street Footwear to Women's Apparel, each with its unique profit margin. The collaboration with these retailers not only extends our reach into various market segments but also leverages their unique strengths to enhance product availability and consumer choice. This strategic selection of retailers, combined with our varied product lineup, positions us well to maximize both market appeal and profitability.
##### We utilize the pd.to_datetime method to convert our date information into a datetime format, enabling precise time-based analysis. Subsequently, we categorize the data according to seasons within the dataframe. This classification leads to the creation of separate dataframes for each season across the different years, facilitating a more detailed and seasonal analysis of the data.

### 2.2.Sales and profits
### 2.2.1.Seasonal revenue
![Sales Profit Product](https://github.com/vicenclleixa/Adidas-US-Sales-2020-2021/blob/main/plots/Sales%20Season.png?raw=true)
##### The bar-plot illustrates Adidas sales by season in the United States over the years 2020 and 2021.

##### In 2020, the sales performance of Adidas in the United States demonstrated varying trends across the seasons. During Spring 2020, sales were at a substantial $59.2 million. However, as the year progressed into Summer 2020, there was a noticeable decrease in sales, which dropped to approximately $45.9 million. The trend of diminishing sales persisted into Autumn 2020, with the figures falling further to around $37.8 million. Despite the previous downward trajectory, Winter 2020 saw a slight uptick in sales, rising to about $39.3 million. This pattern suggests a fluctuating consumer demand and possibly changing market conditions throughout the year.

##### **In 2021, Adidas experienced a remarkable upswing in sales within the United States. The season of Spring 2021 heralded this surge, with sales skyrocketing to around $150.5 million**, marking the most significant increase seen on the chart. This spike may be the result of a confluence of factors, including the relaxation of pandemic-induced restrictions, aggressive marketing initiatives, introductions of new product lines, or a shift in consumer buying patterns. **As the year progressed into Summer 2021, the upward momentum did not wane; sales soared to the chart's zenith at approximately $216.5 million**. Heading into Autumn 2021, a slight contraction in sales volume was observed, yet the numbers were still impressive at around $171.7 million. Concluding the year, Winter 2021 maintained a steady course, with sales figures holding firm at about $179.1 million, indicating a stabilization in the market following the earlier extraordinary growth.

##### The analysis of Adidas' sales data from 2020 to 2021 reveals some general observations about the company's performance in the United States. There was a significant sales growth in 2021 when compared to the previous year, potentially driven by an economic resurgence following the COVID-19 pandemic, which led to increased commercial activity and bolstered consumer purchasing power. A seasonal pattern is also apparent, with warmer seasons, namely spring and summer, registering stronger sales figures than the cooler seasons of autumn and winter, a trend that was particularly pronounced in 2021. **Moreover, a striking revelation is the comparison of spring sales between the two years; the sales in spring 2021 more than doubled those in spring 2020, suggesting a considerable shift in either market dynamics or the strategic direction of the company.**

### 2.2.2.Revenue and Earnings by City
![Sales Profit City](https://github.com/vicenclleixa/Adidas-US-Sales-2020-2021/blob/main/plots/Sales%20profit%20City.png?raw=true "Sales Profit City")

##### This two plots I've developed illustrate the performance of Adidas in terms of sales and profit across the top 20 cities in the United States for the years 2020 to 2021. **The first plot delineates the total sales per city, with Charleston leading at nearly $40 million, followed closely by New York with approximately $39.8 million, and San Francisco at around $34.5 million.** On the other end of the spectrum, the cities with the least sales include Minneapolis, Des Moines, and Omaha, with sales figures ranging from approximately $7.4 million to $5.9 million, underscoring a wide disparity in sales performance across different urban markets.

##### Shifting focus to the most profit by city, the second plot reveals that **Charleston not only led in sales but also in profitability, with an operating profit exceeding $15.6 million.** New York and Miami follow, with profits of roughly $14 million and $12.2 million respectively. This data underscores the fact that high sales volume does not necessarily equate to high profitability, as seen with cities like Los Angeles, which, despite being among the top in sales, ranked eleventh in profit.

##### The selection of these top 20 cities for visualization purposes is strategic, aiming to communicate a clear and concise message regarding where Adidas is thriving in terms of sales and profit. This approach simplifies the message, making it easier to digest and focus on the areas that are most critical to Adidas' success in the US market.

##### The two plots, when examined side by side, offer a comprehensive view of Adidas' financial health across different regions. Notably, they allow for a comparative analysis of which cities not only contribute most to sales but also which ones manage to convert those sales into significant profit, providing valuable insights into market efficiency, cost management, and the overall success of Adidas' business strategies within these urban locales.

### 2.2.3.Revenue and Earnings by Region
![Sales Profit Region](https://github.com/vicenclleixa/Adidas-US-Sales-2020-2021/blob/main/plots/Sales%20profit%20Region.png?raw=true "Sales Profit Region")
##### In my analysis of the sales and profit data for Adidas across various regions in the USA from 2020 to 2021, I found that **the West region exhibits the strongest performance in both categories**. With total sales reaching nearly $269.9 million, the West significantly outpaces the other regions. This level of sales suggests a robust demand and effective market penetration in this area, which may be indicative of a strong brand presence and consumer preference.

##### The Northeast follows as the second-highest in sales with approximately $186.3 million, despite having a dense population and numerous urban centers, which hints at varying regional market dynamics. The Southeast and the South regions show considerable sales as well, at around $163.2 million and $144.7 million, respectively, demonstrating Adidas' solid presence across diverse geographical areas.

##### However, the Midwest reflects the least sales among the regions I analyzed, with sales totaling about $135.8 million. This figure could reflect a range of factors from economic conditions, consumer preferences, to the competitive landscape, which may differ significantly from those in the leading regions. It's important to consider these regional characteristics when strategizing for growth and expansion.

##### **In terms of profitability, the West again leads with an operating profit of approximately $89.6 million. This not only illustrates high sales volumes but also effective operational efficiencies that may include well-managed costs and successful marketing strategies.** The Northeast and the South also report substantial profits, but it is worth noting that despite lower sales, the South's operating profit is close to that of the Southeast, suggesting higher profit margins.

##### These insights into the sales and profits by region for Adidas are crucial for making informed strategic decisions. Understanding the disparities across different regions can help in tailoring region-specific strategies that could involve targeted marketing campaigns, adjusted pricing strategies, or even supply chain optimizations to improve overall performance, particularly **in regions like the Midwest where there is room for growth.**

### 2.2.4.Revenue and Earnings by State
![Sales Profit State](https://github.com/vicenclleixa/Adidas-US-Sales-2020-2021/blob/main/plots/Sales%20profit%20State.png?raw=true "Sales Profit State")
##### Upon reviewing the sales and profit data for Adidas by state in the USA from 2020 to 2021, I observed several key points in the data I've plotted. **New York tops the list with the highest total sales amounting to approximately $64.2 million, followed closely by California with sales of about $60.1 million, and Florida with $59.2 million.** These leading states suggest a strong consumer base and market presence for Adidas, likely benefiting from large populations and robust economic conditions that favor retail growth.

##### Texas also shows significant sales figures at roughly $46.4 million, yet there is a noticeable drop from the top three states, indicating regional differences in sales performance. The data for other states like South Carolina, Washington, and North Carolina, with sales ranging from $29.3 million to $23.9 million, reflects a strong market presence but also suggests there is potential for growth.

##### On the lower end of the sales spectrum, I notice states like **North Dakota, Wisconsin, Iowa, Minnesota, and Nebraska**, where sales figures are comparatively lower, ranging from approximately $7.7 million to $5.9 million. This could point to less market penetration or lower demand, and these figures could be critical for Adidas when considering strategic market initiatives or targeted marketing campaigns to boost sales in these regions.

##### In terms of profit, the data I've plotted showcases a different set of leaders with Charleston, New York, and Miami taking the top spots. This variation between sales and profit figures across states indicates different operational efficiencies, cost structures, and potentially varying consumer behaviors that affect profitability.

##### As I analyze these results, it becomes clear that while certain states present robust sales and profit figures for Adidas, there are others with room for improvement. Understanding why certain states like North Dakota, Wisconsin, Iowa, Minnesota, and Nebraska are at the lower end could be key to unlocking new opportunities for market expansion and increased sales for Adidas in the future.
![US Map](https://github.com/vicenclleixa/Adidas-US-Sales-2020-2021/blob/main/plots/US%20map.png?raw=true "US Map")
![Alaska Map](https://github.com/vicenclleixa/Adidas-US-Sales-2020-2021/blob/main/plots/Alaska%20map.png?raw=true "Alaska Map")
##### **The Map Plot I've crafted here, with Alaska shown separately, delineates the sales distribution throughout the states.** The map employs a color gradient as a direct measure of sales volume, where a deeper hue denotes greater sales. This chromatic stratification facilitates an instant visual identification of the states that are contributing the most to sales revenue, granting an intuitive and straightforward grasp of the geographical dynamics of sales performance. This visual tool is particularly useful for highlighting regional market strengths and pinpointing areas with potential for growth.

### 2.2.5.Sales and Profit Comparison: California vs. Florida
![California Florida Sales Profit Product Comparison](https://github.com/vicenclleixa/Adidas-US-Sales-2020-2021/blob/main/plots/California%20Florida%20Sales%20Profit%20Product%20comparisson.png?raw=true "California Florida Sales Profit Product Comparison")

##### In this graph I've developed, we're exploring the sales and profit data for Adidas in California and Florida. 

##### At first glance, it's apparent that while California edges out Florida in total sales with approximately $60.2 million compared to Florida's $59.3 million, the story changes when we look at profits. Florida actually surpasses California with reported profits of around $20.9 million against California's $19.3 million. This intriguing discrepancy is what sparked my idea to delve deeper into the data.

##### Breaking down sales by product for each state, we see that categories like Men's and Women's Athletic Footwear, and Apparel generate significant revenue. However, it's particularly interesting to note the variations in profit margins for these products. Despite California's higher overall sales, Florida's strategy or cost structure appears to be more efficient, yielding greater profitability.

##### Reflecting on the operating profit by product, we see that Men's Street Footwear boasts the highest profit at approximately $82.8 million, which is a testament to its popularity and potentially higher margins. Women's Apparel also shows impressive profit figures at around $68.7 million. These categories may have contributed significantly to Florida's leading profit position despite having slightly lower overall sales than California.

##### The shift in positions between sales and profit for these products could be due to a number of factors, such as differences in consumer preferences, pricing strategies, promotional activities, or even the cost of goods sold in each state. It's possible that Florida has optimized its mix of products sold, focusing on those with higher margins, or that operational efficiencies in Florida are better than in California.

##### This analysis underscores a crucial point: higher sales do not always equate to higher profits. It highlights the importance of understanding the underlying profitability of product lines and the efficiency of business operations. As a result, this graph not only presents data but also tells a story of market dynamics and strategic financial management within Adidas' operations in different states.

### 2.2.6.Revenue and Earnings by Retailer

![Sales Retailer](https://github.com/vicenclleixa/Adidas-US-Sales-2020-2021/blob/main/plots/Sales%20retailer.png?raw=true "Sales Retailer")

##### In this plot I've developed, we're looking at the sales figures for Adidas products across various retailers from 2020 to 2021 in the USA. The plot reveals that Foot Locker leads as the retailer with the highest sales, reaching towards the 200 million mark, which underscores their strong market presence and perhaps a focused strategy on selling athletic wear.

#### Following Foot Locker, we have Sports Direct and Kohl's, both of which also show significant sales figures but do not quite reach the same heights as Foot Locker. Their positions suggest that while they are important outlets for Adidas products, there are differences in sales performance that could be attributed to their customer base, store locations, or marketing strategies.

#### Interestingly, Amazon, a giant in the retail space, reports lower Adidas sales than the specialized athletic retailers. This could reflect the competitive nature of online marketplaces and the vast diversity of brands available, which might dilute the concentration of sales for any single brand.

#### Finally, Walmart shows the lowest sales among the depicted retailers. This could be due to a variety of factors including Walmart's broader market focus, which may not align as strongly with Adidas' target demographic, or it could be due to the availability and variety of Adidas products offered at Walmart stores.

#### This sales data is crucial for Adidas as it informs the company about which retail partnerships are most fruitful and where there might be room to grow or improve their retail strategies. Understanding these dynamics can help Adidas in negotiating terms with retailers, planning marketing strategies, and making decisions about product distribution.

### 2.2.7.Revenue and Earnings by Product
![Sales Profit Product](https://github.com/vicenclleixa/Adidas-US-Sales-2020-2021/blob/main/plots/Sales%20profit%20product.png?raw=true "Sales Profit Product")

##### In Section 2.2.5 of our analysis, we began to notice distinct differences in profit across various product categories for Adidas sales in the USA from 2020 to 2021. The provided plots illustrate a comparison between the number of units sold and the operating profit for each product category.

##### Starting with sales, **Men's Street Footwear stands out as the top-selling category**, showing that this product line resonates strongly with consumers, leading to high unit sales. **Men's Athletic Footwear and Women's Apparel also show robust sales figures**, which suggests that these categories are popular among Adidas' offerings.

##### However, when we shift our focus to operating profit, the narrative takes an interesting turn. **Despite Men's Street Footwear leading in sales, it is Men's Apparel that appears to lead in profitability**. This suggests that Men's Apparel commands higher profit margins compared to Men's Street Footwear, which could be due to a variety of factors such as pricing strategies, production costs, or a higher perceived value leading to greater willingness to pay among consumers.

##### Similarly, Women's Street Footwear, while being the least sold in terms of units, does not fall at the bottom in terms of profit. This could indicate that **despite lower sales volumes, the profit margins on Women's Street Footwear are substantial, which can compensate for the lower unit sales.**

##### These disparities between sales and profit accentuate the importance of not just selling volume but also selling the right mix of products that contribute to overall profitability. It is crucial for Adidas to continue to evaluate and strategize around these variances to optimize both their product portfolio and pricing strategies to enhance profitability.
