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
   1. [Crunchbase Accelerator University Data](https://github.com/dmathe18/crunchbase_vc_cluster_analysis/blob/main/crunchbase_filtered_data.xlsx) \(mrc\_table10\): this dataset contains information about 1,950 venture capital firms and investors, describing characteristics such as number of investments, number of exits, location, description, and investor type.


## Data Question - Analysis

We’ll use Microsoft Excel to answer:

* **What did the US college landscape look like in 2000 and 2013?** Exploring general college data regarding enrollment, sticker price, expenditures, and other related metrics per university "tier" or ranking
* **How do parents’ and kids’ income data relate college tier?** Exploring the relationship between income distributions of students/parents entering colleges at different types of higher education institutions
* **How do colleges contribute to social mobility?** Exploring how students' income distribution changes when they are around the age of 35 \(likely earning a stable income instead of in between jobs or in graduate school\)
* **Is 'percentage of Pell-eligible students' a good metric to define student income diversity? What other metrics should JHU monitor to continue to develop a more robust student body and subsequent alumni network?** Exploring specific metrics related to Pell grant recipients to see how colleges can use this percentage--or other--metric\(s\)--to measure their social mobility impact 

## Data Answer

Looking at colleges in general, we can start to understand the US higher education landscape in different categories, such as college "tier" or combination of selectivity and rank in 200.

#### How many colleges are in each tier?

![](.gitbook/assets/university-tier-counts.png)

Here we can see that two-year public and private higher education institutions make up most of the volume of colleges in the US, followed by "selective private" and "selective public" schools. As we might expect, there are very few "Ivy Plus" schools \(highly selective and highly ranked\), "other elite" schools \(including Johns Hopkins\), and "highly selective" public and private schools \(perhaps less than one per state\). This gives us an idea of the type of quantitative impact that education or admissions reform might have based on what type of institutions the reform focuses on.

#### What's the average sticker price for higher education institutions at each tier?

![](.gitbook/assets/final-chart.png)

Here we see almost an opposite type of distribution--the highly selective private schools have the highest sticker price, and the two-year not-for-profit institutions have the lowest sticker price. We should also note that the sticker price also does not necessarily reflect the price that students need to pay to attend the institution, however, it can give us insight into the type of students who attend those schools and who don't receive financial aid. Additionally, highly selective public schools have a significantly lower sticker price than their peer institutions, so this may indicate that students could get a better "bang for their buck" here if the student outcomes are similar to peer institutions. 

#### How does income distribution compare at different university tiers?

![](.gitbook/assets/parent_income_dist_by_tier.png)

We can also look at the average income distribution at the different higher education tiers where Q1 indicates families in the lowest income quintile and Q5 indicates families in the highest income quintile. We can see that the income distribution starts to even out when we look at nonselective four-year colleges and that elite and other highly selective institutions are predominantly filled with students from the highest income quintile.

#### How do colleges at different institutions play a role in their students' social mobility?

![](.gitbook/assets/student_income_mobility_by_tier.png)

To understand more about how colleges contribute to social mobility, we can compare the average income "standing" of students based on their tax records approximately 10 years after graduating from college. Even though all schools have students from all five income quintiles, students from similarly tiered universities end up at about the same income distribution level, regardless of their position entering college. This gives us insight into the potential impact that a specific university or tier of universities can have on social mobility and how this impact differs between different schools. It's important to note here though, that this visual doesn't give us insight into how many students come into college at each income quintile, which would affect the net social mobility impact from any specific university.

#### What do Pell Grants tell us about how a college contributes to social mobility and university diversity?

![](.gitbook/assets/q1_q2_pell_college_data.png)

While President Daniels mentions "Pell-eligible" students as a metric for Johns Hopkins to measure their  students' socioeconomic diversity, we may want to explore what this looks like in terms of Pell Grant recipients at institutions to gain some insight into the type of financial support that low income students receive to attend these institutions. [Pell eligibility](https://www.usnews.com/education/best-colleges/paying-for-college/articles/everything-you-need-to-know-about-the-pell-grant) is based on several factors including students' and parents' income and college cost and full-time vs. part-time status. Pell Grants are not the only kind of financial aid that students can receive, however, this could give us insight into how much support students have at different institutions compared to the distribution of the lowest two income quintiles. What else could the Pell recipient data tell us about the institution?

## Business Answer
