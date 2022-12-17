---
title: "Price recommendation for Airbnb hosts post-pandemic"
date: 2022-12-17
published: true
tags: [dataviz, altair, hvplot, holoviews]
excerpt: "Embedding interactive charts on static pages using Jekyll."
hv-loader:
  hv-chart-1: ["charts/price_dot.html", "500"]
  hv-chart-2: ["charts/price_neighbor.html", "500"]
  hv-chart-3: ["charts/point_validation.html", "500"]
  hv-chart-4: ["charts/neighbor_validation.html", "500"]

toc: false
toc_sticky: true
---


![features]({{ site.url }}{{ site.baseurl }}/assets/images/feature/features.png)


## Reasons Behind the Yield Difference (hvplot)  

After calculating the monthly yields of Airbnb listings, we classified the results into 3 categorys: high yield(top 30%), median yield(30%-70%), low yield(70%-100%).In this part, we decided to do some simple comparison among different yields' Airbnb.

To begin with, we compared the `host_year` among different yield types. A interesting finding is that the new hosts' Airbnb seems to earned more than those experienced hosts.
<div id="hv-chart-1"></div>  
---- 
In terms of the host response time, the high-yield Airbnb host's response time is much higher than the median-yield hosts and low-yields hosts, most of them response to the guests within an hour.
<div id="hv-chart-2"></div> 
---- 

<div id="hv-chart-3"></div> 

<div id="hv-chart-4"></div> 





## Notes

- See the [raw source code]([https://raw.githubusercontent.com/MUSA-550-Fall-2021/github-pages-starter/main/_posts/2021-11-29-measles-charts.md](https://raw.githubusercontent.com/MUSA-550-Fall-2022/github-pages-starter/main/_posts/2019-04-13-measles-charts.md)) of this post for details on how these charts were embedded.
- See the [lecture 13A slides](https://github.com/MUSA-550-Fall-2022/week-13/blob/main/lecture-13A.ipynb) for the code that produced these plots.

**Important: When embedding charts, you will likely need to adjust the width/height of the charts before embedding them in the page so they fit nicely when embedded.**
