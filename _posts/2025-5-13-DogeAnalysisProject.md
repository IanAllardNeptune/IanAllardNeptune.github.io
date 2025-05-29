---
layout: post
title: DOGE.gov Analysis
subtitle: An analysis of the Doge.gov website.
cover-img: /assets/img/DOGEBanner.png
thumbnail-img: /assets/img/DOGEBanner.png
share-img: /assets/img/DOGEBanner.png
tags: [Mental, AI]
author: Ian Allard-Neptune
---


# Introduction

My project is to analyze the DOGE.gov website. The DOGE department of the United States Government is the Department of Government Efficiency. Spearheaded in the second Trump Administration primarily by Elon Musk, the department focuses on cutting down on costs from various government sectors by what it deems unnecessary spending. Siding with the Trump administration's general interests, the defunding and rejection of renewing grants is driven by political agendas. For example, the NY Times discovered that government documents containing [this list](https://www.nytimes.com/interactive/2025/03/07/us/trump-federal-agencies-websites-words-dei.html) of words are disappearing from records. It is difficult to determine what is "saving" and what is just the Trump administration pushing its ideology.


In addition to the removal of several key contracts, multiple articles and papers have exposed inaccuracies in the false claims the DOGE.gov website provides. The main page of the savings section sums up all of the contracts that they claimed to have saved. The main goal of my project is to detect inaccuracies across the website in what they claimed to have saved. There are a couple of places that I am analyzing to compare the data they present and what the reality is. The first place is [the API](https://api.doge.gov/docs) that they provide.


##### These two graphs are derived from data scraped from the API. Specifically, the grants and leases:

### Grants - Value/Savings

<div class="flourish-embed flourish-chart" data-src="visualisation/23013223"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/23013223/thumbnail" width="100%" alt="chart visualization" /></noscript></div>

### Leases - Value/Savings

<div class="flourish-embed flourish-chart" data-src="visualisation/23491096"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/23491096/thumbnail" width="100%" alt="chart visualization" /></noscript></div>


The Value/Savings for the grants does not reveal much and seems as though to could be quite accurate. However, the same cannot be said for the leases. On the left side of the graph, the farthest outlier of the group "Termination Via Mass Mod" claims to save almost double what the leases are valued at. After doing further research and creating two more graphs.

Leases Pie Chart of Summed Costs 

<div class="flourish-embed flourish-chart" data-src="visualisation/23485111"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/23485111/thumbnail" width="100%" alt="chart visualization" /></noscript></div>

Leases Pie Chart of Amount 

<div class="flourish-embed flourish-chart" data-src="visualisation/23485537"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/23485537/thumbnail" width="100%" alt="chart visualization" /></noscript></div>

From analyzing these two graphs, it is clear that something is off in the recorded data. The savings of the leases are significantly higher than the value of the contracts and account for around $250,000,000, which we don't understand where it came from. 


### Moving to the Doge Scraping

While I did get some interesting information from the API and found some errors in the data that they reported, the data is only valuable when comparing it to other data to see if they agree. So I decided to look at the website itself. This process was remarkably difficult! Due to the pages being made with JavaScript, I could not scrape through a changing URL like I did for the API. This forced me to use Selenium to select the next page to gather new data. However, this led to a plethora of 403 errors. 403 Errors, of course, are ones that mean the website understands the request but rejects it.

After trying variations of selenium and an application called HTTracker, nothing worked. This led me to shift plans as I could not figure out how to scrape the site with the tools that I knew. This led me to change strategies as I downloaded the html from a sample 50 pages of the highest value contracts.

Immediately, upon seeing the values in the CSV, I noticed an apparent problem with the data, as many of the FPDS links for them were unavailable due to legal reasons. Here are some graphs to explain the extent to which the data was unavailable: 

#### FPDS - Number of Entries From Each Vendor

<div class="flourish-embed flourish-chart" data-src="visualisation/23475802"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/23475802/thumbnail" width="100%" alt="chart visualization" /></noscript></div>

#### FPDS - Sum of "Savings" From Scraped Doge

<div class="flourish-embed flourish-chart" data-src="visualisation/23475829"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/23475829/thumbnail" width="100%" alt="chart visualization" /></noscript></div>

As detected from the first 500 entries, 289 of the entries are unavailible which accounts for a little less than 11 billion dollars! While I only sampled the first 500 contract entries it is safe to say that there is a massive problem with transparency of those entries.


### Comparing the Two

Lastly, comparing the scraped website and the API csvs posed a difficult problem for several reasons. Firstly, the API csv contained around 9,600 entries compared to the sample csv of the website which contained only 500. Another problem was that the entries did not clearly match up one-one. Only some of the keys in either csv were the same. The two keys that I determined would be most helpful for comparing two entries from either would be the "Agency" and "Vendor" keys. I wrote code which overlapped the csvs by creating a new csv that was filled with the entries that overlapped with agency and vendor. This decreased my sample size from 500 to an even smaller 94 entries! Here is the resulting graph:

#### API Vs Scraped Website Savings

<div class="flourish-embed flourish-chart" data-src="visualisation/23474988"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/23474988/thumbnail" width="100%" alt="chart visualization" /></noscript></div>

In the results it became clear that the entries aligned perfectly and that the savings on the website agree with the provided API.


## Conclusion


While my specific hypothesis of comparing the website to its API did not prove true, I find this conclusion FAR from proving benevolence in the DOGE department. While the numbers they provide may align with governmental documents, they mislead by failing to illustrate where the numbers come from. A department that claims to revolutionize transparency in government spending cannot simultaneously claim “Unavailable for legal reasons” for a massive portion of their provided data









