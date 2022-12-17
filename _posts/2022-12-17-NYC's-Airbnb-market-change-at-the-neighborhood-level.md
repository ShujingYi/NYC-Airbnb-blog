---
title: "Influence of the pandemic on NYC's Airbnb market"
date: 2022-12-17
published: true
tags: [dataviz, matplotlib, seaborn]
excerpt: "This is an example blog post that embeds a matplotlib image."
toc: true
toc_sticky: true
read_time: false
---

# Section 1

This is an example post. The posts are written in markdown.



## Exploratory Analysis of New York Airbnb Dataset (seaborn)
Below, we plot the histogram of Airbnb Price in New York,and found that most of Airbnb listings ranged from $60 to $160.

![countlisting]({{ site.url }}{{ site.baseurl }}/assets/images/listing_counts.png)

In terms of the average price by neighbourhood group, the Manhattan and Brooklin is much higher than Queens, Staten Island and Bronx, which explains why there are more Airbnbs in these two areas.  

![boxprice]({{ site.url }}{{ site.baseurl }}/assets/images/price.png)

Is Airbnb price and the number of Reviews per month related with each other? The following figure tells us that the more reviews there are, the lower the price of the Airbnb might be, which means that cheaper Airbnb seems to have higher occupancy rate. Besides, the price of entire home is much higher than private room.  

![barreview]({{ site.url }}{{ site.baseurl }}/assets/images/review_per_month.png)

Then, we also explored the relationship between `host_year` (the year that host opened the Airbnb) and the count of different Airbnb types.There is a general upward trend of new Airbnb listings, and both of the entire apt and private room seems to have a absolute big market share. Besides, an interesting finding is that the private room seems to have become a more popular chioce than the entire home for Airbnb host since 2015.   

![barscore]({{ site.url }}{{ site.baseurl }}/assets/images/review_scores_rating.png)
