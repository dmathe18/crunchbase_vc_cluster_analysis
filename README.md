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

![ipo_linear_regression](https://user-images.githubusercontent.com/78438582/117337530-53b73900-ae52-11eb-9470-aebee346d882.png)

This scatter plot charts the relationship between total number of investments and number of IPOs. The R-squared value of .9049 indicates that 90.49% of the variation in the number of IPOs is explained by the variation in the number of investments. In other words, there is a strong, positive correlation between total investments and the number of IPOs. This is important because it suggests a linear proportional correspondence between the two variables, making it appear unlikely that larger firms outperform smaller firms in terms of number of IPOs as a proportion of total IPOs. Stated differently, the graph seems to suggest that larger firms have attracted more interest than smaller firms for reasons other than their ability to take companies public. 

#### What is the relationship between total number of investments and number of diversity investments?

![diversity_linear_regression](https://user-images.githubusercontent.com/78438582/117337561-5dd93780-ae52-11eb-91f4-2b8e80874fda.png)

This graph shows a strikingly similar relationship between total investments and number of diversity investments. The R-squared value of .9698 indicates that 96.98% of the variation in the number of diversity investments is explained by the variation in the total number of investments. Similar to the previous graph, there is a strong, positive correlation between total investments and the number of diversity investments. While the 6 data points with over 1,000 total investments may be considered outliers with respect to the rest of the data, the visualization seems to imply that the total investments offers high predictive value for the number of diversity investments. This may be important to investors seeking to interpret the meaning behind a high level of diversity investments made by a particular VC firm— in particular, it suggests that for many companies, high levels of diversity investments may be more a function of total number of investments rather than any particular interest in increasing the representation of diverse entrepreneurs among its investments. 

#### How could the set of 279 venture capital firms and investors included in the filtered Crunchbase accelerator university dataset be clustered according to IPO exits, diversity, and total investments?

![Screen Shot 2021-03-18 at 12 36 12 PM](https://user-images.githubusercontent.com/78438582/111662741-93fd2200-87e6-11eb-867f-e6163f559dc8.png)

The image above displays the results of the cluster analysis performed for the 279 venture capital firms and investors represented in the data set. Three clusters were used in the analysis, with the Excel solver finding a minimum squared distance of 81.56 for the grouping achieved. The first cluster— Microsoft Accelerator Seattle— represents VC firms with approximately average total investments, IPO exits, and diversity investments. The second cluster— MassChallenge— represents VC firms with a high level of total investments but a less-than-proportional number of IPOs and diversity investments. The third cluster— Techstars— represent firms with extremely high levels of total investments, IPOs, and diversity investments. 

![cluster_anchor_frequency](https://user-images.githubusercontent.com/78438582/117337900-c9bba000-ae52-11eb-8912-c1e1adb94e25.png)

As we can see, the vast majority of venture capital firms in the data set can be grouped in with the first cluster, suggesting that most of the firms have about the same level of total investments, IPO exits, and diversity investments. The z score for these firms is likely negative due to the long right tail of the distribution caused by the six outliers mentioned above. Three firms can be grouped in with the second pool— those with high level of total investments but a less-than-proportional number of IPOs and diversity investments. Three other firms are a part of the third cluster, which represent firms with extremely high levels of total investments, IPOs, and diversity investments. 

![cluster_anchor_by_org](https://user-images.githubusercontent.com/78438582/117337936-d50ecb80-ae52-11eb-8ace-cc83ab7a283c.png)

The graph above shows the cluster anchor of each organization/person number, with 1 corresponding to the first entry in the dataset, 2 corresponding to the second entry in the dataset, and so on. This chart provides another view of the overwhelming representation of cluster 1 firms as a fraction of the whole.


## Data Interpretation
The objective of this analysis was to create a logical, coherent grouping of the 279 organizations represented in the dataset, differentiated along variations in total investments, IPO exits, and diversity investments. The analysis found a high level of similarity among most of the firms, with notable exceptions in the second and third clusters. While diversity investments and IPOs appeared to strongly correlated with total investments, the second cluster provides a notable exception. These firms had a high level of total investments but a less-than-proportional number of IPOs and diversity investments. This information could potentially be useful to entrepreneurs looking to take their companies public or filtering their funding search by firms that offer the highest level of diversity investments. In practice, firms in the first cluster to should be interpreted to represent the average VC firm with average total investments, diversity investments, and IPO exists. The second cluster represents firms that entrepreneurs seeking diversity investments or a strong track record of IPOs should avoid. The third cluster represents outliers— proportionally, these firms do not offer substantially better prospects for diversity investments or IPOs than cluster 1 firms. 

Additional data that may be useful for further analysis includes information and statistics on alternative exit options (i.e., other than IPOs). It would be interesting to see if performing a cluster analysis along another metric of performance would help to meaningully differentiate the firms beyond the IPO and diversity investment cluster analysis above. Other datasets that list different kinds of VC firms and which may help differentiate cluster 1 include Chicago Blend's [Chicago VC Diversity](https://data.world/chicagoblend/chicago-vc-diversity) dataset which aggregates employee data across 70 Chicago-based venture firms in October 2018 to understand the employee makeup of Chicago's firms, and the [CB Insights 2014 Seed Investor](https://data.world/rickd/cb-insights-2014-seed-investor) dataset which lists information about the most active seed investors. 




## Step-by-step Instructions for Excel Data Analysis
1. Download [Crunchbase Accelerator University Data](https://github.com/dmathe18/crunchbase_vc_cluster_analysis/blob/main/crunchbase_filtered_data.xlsx) dataset from Github repository
2. Transform data into table using Excel table feature
3. Identify columns of interest; highlight those columns and remove blanks using filter feature
4. Copy data and transfer to second sheet
5. Delete unused columns, add 9 rows above for cluster analysis, and add 1 column to number the VC firms
6. Create scatter plots using recommended charts; edit axes lables and title
7. Calculate mean and average of each column
8. Use mean and average values to compute z scores for each column
9. Use SUMXMY2 function to calculate distance to cluster 1 squared, distance to cluster 2 squared, and so on
10. Use MIN function to identify and list the minimum squared distance
11. Use match function to display the anchor corresponding to the minimum distance squared
12. Use Solver Data Analysis add-on to compute the clusters that minimize the sum of the minimum distances
13. List cluster anchors in separate column; use COUNTIF function to calculate the frequency of each anchor
14. Create graphs displaying frequency of each cluster and the cluster to which each organization corresponds
