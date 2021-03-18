# crunchbase_vc_cluster_analysis
This repository contains the original excel documents, analyzed excel documents with Excel formulas and data visualizations, and a README file that summarizes findings from a cluster analysis performed for the Crunchbase early stage venture capital database.

# Classifying Venture Capital Firms by IPO Exits, Diversity, and Total Investments

## Background
According to research published by Stifel Financial Corporation in 2019, "the U.S. IPO Market ended the decade with another impressive year with over 200 IP0s priced (including SPACs) behind strong U.S. stock performances and low volatility." An initial public offering, or IPO, refers to the process by which a privately owned corporation offers its shares to the primary market via stock issuances. Taking a company public through an IPO typically takes between 6 to 9 months, pursuant to oversight and regulations by the Securities and Exchange Commission. For a company's founders, executive-level managers, and early investors, IPOs represent a major milestone in a company's life cycle, and can be seen as an effective exit strategy for stakeholders seeking to realize the full profit from their private investment.

[The National Bureau of Economic Research](https://www.nber.org/digest/apr07/changing-business-volatility) observes that publicly traded companies "constitute less than 1 percent of all U.S. firms and about one-third of U.S. employment in the non-farm business sector." With the prospects of soaring valuations, unparalleled liquidity, and institutional investor interest driving the crescendo in the IPO pipeline in 2020, private executives are increasingly looking to IPOs as a way to capitalize on their investments and take advantage of improving investor sentiment about the post-pandemic economic recovery. PricewaterhouseCoopers, the second-largest global professional services network and accounting firm, states that depite the COVID-19-related new issuance slowdown at the beginning of the year, "2020 US equity issuance is the [highest on record](https://www.pwc.com/gx/en/services/audit-assurance/ipo-centre/global-ipo-watch.html) ($460.9bn), with all major sub-products such as IPOs and FOs also breaking the record."

With over [1000 active venture capital firms](https://iveybusinessjournal.com/publication/venture-capital-firms-in-america-their-caste-system-and-other-secrets/) in the United States according to the National Venture Capital Association, entrepreneurs have an array of competitive options to source funding from. Along what metrics should private company founders differentiate between venture capital firms? What insights can we gain about the level of experience of managers and advisors from comparing the number of IPO exits across venture capital firms? How might we cluster a set of VC firms based on IPO exits, diversity, and total investments? We’ll take a look at open data from [Crunchbase](https://www.crunchbase.com) to explore answers to these questions and see how particular venture capital firms and investors might appropriately be grouped according to the above criteria. 


## Business Question

_**How might a set of 279 venture capital funding sources be grouped or clustered according to IPO exits, diversity, and total investments?**_


## Data Question - Open Data

We'l use open data from one source: 

1. **Crunchbase**: Crunchbase works with partners to maintain the highest quality company information while enabling world-class research on investment trends and business ecosystems. Leverageing 400+ algorithms and its netowork of 600,000+ executives, entrepreneurs, and investors, the platform validates is data on a daily basis and follows over 2,000 of the top news publications to ensure it captures every notable funding round, acquisition, and exit. We will use one dataset from this study:
   1. [Crunchbase Accelerator University Data](https://github.com/dmathe18/crunchbase_vc_cluster_analysis/blob/main/crunchbase_filtered_data.xlsx): this dataset contains information about 1,950 venture capital firms and investors, describing characteristics such as number of investments, number of exits, location, description, and investor type.


## Data Question - Analysis

We’ll use Microsoft Excel to answer:

* **What is the relationship between total number of investments and number of exits (IPO)?** 
* **What is the relationship between total number of investments and number of diversity investments?** 
* **How could the set of 279 venture capital firms and investors included in the filtered Crunchbase accelerator university dataset be clustered according to IPO exits, diversity, and total investments?** 


## Data Answer

We begin by creating scatter plots of IPO exits and diversity investments with respect to total number of investments, and proceed with a cluster analysis of the data which categorizes the observations such that the objects in each group are similar, and the objects in each group are substantially different from the objects in other groups.

#### What is the relationship between total number of investments and number of exits (IPO)?

![Screen Shot 2021-03-18 at 12 30 38 PM](https://user-images.githubusercontent.com/78438582/111662034-f1dd3a00-87e5-11eb-8fd5-f1e20a8c03f0.png)

This scatter plot charts the relationship between total number of investments and number of IPOs. The R-squared value of .9049 indicates that 90.49% of the variation in the number of IPOs is explained by the variation in the number of investments. In other words, there is a strong, positive correlation between total investments and the number of IPOs. This is important because it suggests a linear proportional correspondence between the two variables, making it appear unlikely that larger firms outperform smaller firms in terms of number of IPOs as a proportion of total IPOs. Stated differently, the graph seems to suggest that larger firms have attracted more interest than smaller firms for reasons other than their ability to take companies public. 

#### What is the relationship between total number of investments and number of diversity investments?

![Screen Shot 2021-03-18 at 12 31 13 PM](https://user-images.githubusercontent.com/78438582/111662138-0d484500-87e6-11eb-87f8-9a63d7b8a360.png)

This graph shows a strikingly similar relationship between total investments and number of diversity investments. The R-squared value of .9698 indicates that 96.98% of the variation in the number of diversity investments is explained by the variation in the total number of investments. Similar to the previous graph, there is a strong, positive correlation between total investments and the number of diversity investments. While the 6 data points with over 1,000 total investments may be considered outliers with respect to the rest of the data, the visualization seems to imply that the total investments offers high predictive value for the number of diversity investments. This may be important to investors seeking to interpret the meaning behind a high level of diversity investments made by a particular VC firm— in particular, it suggests that for many companies, high levels of diversity investments may be more a function of total number of investments rather than any particular interest in increasing the representation of diverse entrepreneurs among its investments. 

#### How could the set of 279 venture capital firms and investors included in the filtered Crunchbase accelerator university dataset be clustered according to IPO exits, diversity, and total investments?

![Screen Shot 2021-03-18 at 12 36 12 PM](https://user-images.githubusercontent.com/78438582/111662741-93fd2200-87e6-11eb-867f-e6163f559dc8.png)

The image above displays the results of the cluster analysis performed for the 279 venture capital firms and investors represented in the data set. Three clusters were used in the analysis, with the Excel solver finding a minimum squared distance of 81.56 for the grouping achieved. The first cluster— Microsoft Accelerator Seattle— represents VC firms with approximately average total investments, IPO exits, and diversity investments. The second cluster— MassChallenge— represents VC firms with a high level of total investments but a less-than-proportional number of IPOs and diversity investments. The third cluster— Techstars— represent firms with extremely high levels of total investments, IPOs, and diversity investments. 

![Screen Shot 2021-03-18 at 12 34 13 PM](https://user-images.githubusercontent.com/78438582/111662427-497ba580-87e6-11eb-8176-46bb50e0e6e5.png)

As we can see, the 

![Screen Shot 2021-03-18 at 12 33 15 PM](https://user-images.githubusercontent.com/78438582/111662437-4c769600-87e6-11eb-85b1-654c680d5e09.png)

We can also look at the average income distribution at the different higher education tiers where Q1 indicates families in the lowest income quintile and Q5 indicates families in the highest income quintile. We can see that the income distribution starts to even out when we look at nonselective four-year colleges and that elite and other highly selective institutions are predominantly filled with students from the highest income quintile.

![Screen Shot 2021-03-18 at 12 36 12 PM](https://user-images.githubusercontent.com/78438582/111662741-93fd2200-87e6-11eb-867f-e6163f559dc8.png)


## Data Interpretation

## Step-by-step Instructions for Excel Data Analysis
