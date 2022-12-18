---
title: "NYC's Airbnb market change at the neighborhood level"
date: 2022-12-17
published: true
tags: [Cluster Analysis, hvplot]
excerpt: "Compare listing spatially before/"after" the pandemic and use K-means clustering to recommend places to stay for guests.."
hv-loader:
  hv-chart-1: ["charts/hvplot_list_neighbor.html", "800"]
  hv-chart-2: ["charts/hvplot_price_per_person.html","700"]
  hv-chart-3: ["charts/hvplot_review_scores_rating.html", "600"]
  hv-chart-4: ["charts/hvplot_reviews_per_month.html", "500"]
  hv-chart-5: ["charts/hvplot_bedrooms.html", "400"]
  hv-chart-6: ["charts/hvplot_cluster.html", "300"]
toc: true
toc_sticky: true
read_time: false
---

## Compare Listing Spatially before/"after" Pandemic

![neighborhood]({{ site.url }}{{ site.baseurl }}/assets/images/neighborhood.png)

<div id="hv-chart-1"></div> 

<div id="hv-chart-2"></div>  

<div id="hv-chart-3"></div>  

<div id="hv-chart-4"></div>  

<div id="hv-chart-5"></div>  

## K-means Clustering Analysis
In this part, we clustered neiborhoods by Airbnb stats, trying to find desirable neighbourhoods for different types of Airbnb guests. Firstly, we selected the `price_per_person`,`reviews_per_month`,`review_scores_rating` and `count` as our features, and calculated mean value of thoses featuress by neighbourhood. Secondly, a K-means cluster analysis is performed and the results are devided into 5 labels:

<div id="hv-chart-6"></div>  

For each features, we could calculate the average value per cluster, the results is as follows:
```python
group_cluster.groupby('label')['price_per_person'].mean().sort_values()
```
> label  
> 0    31.247056  
> 4    33.483703  
> 1    37.457584  
> 2    53.109358  
> 3    80.434985  
> Name: price_per_person, dtype: float64  

```python
group_cluster.groupby('label')['review_scores_rating'].mean().sort_values()
```
> label  
> 4    91.364327  
> 2    93.701058  
> 3    94.164047  
> 0    94.923690  
> 1    95.913784  
> Name: review_scores_rating, dtype: float64

```python
group_cluster.groupby('label')['reviews_per_month'].mean().sort_values()
```
> label  
> 3    1.120334  
> 1    1.267650  
> 2    1.274230  
> 4    1.660396  
> 0    2.890525  
> Name: reviews_per_month, dtype: float64  

```python
group_cluster.groupby('label')['count'].mean().sort_values()
```
> label  
> 0      37.510638  
> 4      81.396226  
> 1     106.000000  
> 3     251.360000  
> 2    1938.222222  
> Name: count, dtype: float64  

## Recommendations for Potential Airbnb Guests 

Based on the clustering results, we try to divide our potential Airbnb guests into several categories, and recommended different neighborhoods for each, respectively.

- For **price-sensitive** Airbnb guests, or people who pursue the **highest cost-effective** living experience,the neighbourhoods with label 0 might be their best chioce, since the Airbnb price per person for those areas is the lowest, and the review scores are also relatively high. However, It is worth noting that the Airbnbs in those neighbourhoods might be in high demand, since the Airbnb supply in those areas is small (low count), while the occupancy rate might be really high (with a high reviews_per_month).  
  
- For **quality-conscious** Airbnb guests, the neighbourhoods with label 1 might be their best chioce. The Airbnb in those areas are of high-quality and moderate price. With a reasonable supply and Airbnb count,they don't have to worry too much about those Airbnbs being booked.  
