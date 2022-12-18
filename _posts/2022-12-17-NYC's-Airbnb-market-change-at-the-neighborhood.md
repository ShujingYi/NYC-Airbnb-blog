---
title: " NYC's Airbnb market change at the neighborhood level "
date: 2022-12-17
published: true
tags: [Cluster Analysis, hvplot]
excerpt: "Compare listing spatially and use K-means clustering to recommend places to stay for guests."
hv-loader:
  hv-chart-1: ["charts/hvplot_cluster.html", "500"]
toc: true
toc_sticky: true
read_time: false
---

## Compare Listing Spatially before/"after" Pandemic

![features]({{ site.url }}{{ site.baseurl }}/assets/images/neighborhood.png)


## K-means Clustering Analysis
In this part, we clustered neighborhoods by Airbnb features, trying to find desirable neighborhoods for guests with different demands. We selected the `price_per_person`,`reviews_per_month`,`review_scores_rating`, `bedrooms` and `count` as our features and calculated the mean value of those features by neighborhood. Then we performed K-means cluster analysis, and the results were divided into five labels:

<div id="hv-chart-1"></div>  

For each features, we could calculate the average value per cluster, the results is as follows:
```python
group_neighbor_22.groupby('label')['count'].mean().sort_values()
```
>label
>4      14.400000
>1      50.784091
>3      94.285714
>0     167.763158
>2    1353.200000
>Name: count, dtype: float64 

```python
group_neighbor_22.groupby('label')['price_per_person'].mean().sort_values()
```
>label
>1    42.493588
>3    44.160675
>4    44.939426
>2    66.150279
>0    86.746105
>Name: price_per_person, dtype: float64

```python
group_neighbor_22.groupby('label')['review_scores_rating'].mean().sort_values()
```
>label
>3    4.539298
>2    4.606367
>0    4.665889
>4    4.749952
>1    4.764137
>Name: review_scores_rating, dtype: float64

```python
group_neighbor_22.groupby('label')['reviews_per_month'].mean().sort_values()
```
>label
>2    1.046912
>0    1.133068
>3    1.194759
>4    1.927789
>1    1.991417
>Name: reviews_per_month, dtype: float64

```python
group_neighbor_22.groupby('label')['bedrooms'].mean().sort_values()
```
>label
>3    1.305697
>2    1.343419
>1    1.362601
>0    1.378306
>4    2.483525
>Name: bedrooms, dtype: float64



## Recommendations for Potential Airbnb Guests 

Based on the clustering results, we try to divide our potential Airbnb guests into several categories, and recommended different neighborhoods for each, respectively.

- For **price-sensitive** Airbnb guests, or people who pursue the **highest cost-effective** living experience,the neighbourhoods with label 0 might be their best chioce, since the Airbnb price per person for those areas is the lowest, and the review scores are also relatively high. However, It is worth noting that the Airbnbs in those neighbourhoods might be in high demand, since the Airbnb supply in those areas is small (low count), while the occupancy rate might be really high (with a high reviews_per_month).  
  
- For **quality-conscious** Airbnb guests, the neighbourhoods with label 1 might be their best chioce. The Airbnb in those areas are of high-quality and moderate price. With a reasonable supply and Airbnb count,they don't have to worry too much about those Airbnbs being booked.  



