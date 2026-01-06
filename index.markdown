---
layout: home
---

<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

This website presents, in a format convenient for decision-makers and funders working on caged hen welfare, key data relating to cage-free and caged eggs sold by supermarkets and retailers around the world. Data is updated every quarter.

Specifically, this website aims to present data on **the numbers of cage-free vs caged shell egg products sold by major grocery retailers in specific countries**. This website does *not* include data on sales numbers—rather, the data collects details about products that are available for purchase at major retailers in the specific countries, and whether those products are caged or cage-free.

The purpose of this data is to provide an additional source of information about how many egg products are cage-free as opposed to cage, especially for companies that do not have cage-free commitments or do not report on their commitment. This fills an important gap in our understanding of the cage-free egg market around the world, but this data has little meaning in isolation. Please interpret this data alongside other important publications:

- [2024 Cage-Free Fulfillment Report by Open Wing Alliance](https://openwingalliance.org/2024-cage-free-fulfillment-report)
- [EggTrack by Compassion in World Farming](https://www.eggtrack.com/en/)
- [Chicken Watch](https://chickenwatch.org/progress-tracker/)
- [Cage-Free Tracker by Sinergia Animal](https://www.cagefreetracker.com/)
- [Welfare Footprint Project](https://welfarefootprint.org/laying-hens/)

# Cage-free products by retail chain

<table>
  {% for row in site.data.aggregate_table_current %}
    {% if forloop.first %}
    <tr>
      {% for pair in row %}
        <th>{{ pair[0] }}</th>
      {% endfor %}
    </tr>
    {% endif %}

    {% tablerow pair in row %}
      {{ pair[1] }}
    {% endtablerow %}
  {% endfor %}
</table>

<div class="tablenotes">
  Table notes:<br />
  - This table shows data for the most recent quarter during which data was collected. For historic data, see the downloads below.<br />
  - When calculating the percentage of products that are cage-free for a specific company, we assume that the "insufficient information" category represents caged eggs. This means that the cage-free percentage is a conservative estimate.<br />
  - The "organic" category is assumed to be cage free. This is usually true, but this might be false in some countries.<br />
  - Whether a company has/is reporting on a cage-free commitment is our best guess based on public sources, and we welcome any corrections.
</div>

# Raw/historic datasets  

For your own analysis, you may download the raw data:  

- [The aggregate table for this quarter](data/aggregate_table_current.csv) - this is the table shown above, exactly as you see it.
- [The aggregate table for all time](data/aggregate_table_alltime.csv) - this is the table as shown above, though there is one table for every quarter since we began collecting data. This lets you examine how numbers are changing over time.
- [The raw table for all time](data/raw_table_alltime.csv) - this is the name and details corresponding to every individual egg product. The raw table is the original data underlying the aggregate table (above).

# About the data  
- We only include grocery retailers, such as supermarkets and hypermarkets. We do not include restaurants, food service businesses, and so on. We focus on shell eggs; some retailers include liquid or powered eggs in their online store pages under the "egg" category, and such instances are included in the data. However, where retailers include liquid or powered eggs under a separate category, we made no effort to obtain that data. We have done our best to remove eggs from animals other than chickens (e.g. quails), though we may have missed some.
- Data is systematically scraped from online supermarket and grocery websites. For each country, we have aimed to include all of the major supermarkets and grocery retailers in this country. However, this is not always possible; countries like Japan have a very decentralised retail industry, so it is not possible to achieve wide market coverage in those countries. Likewise, some countries simply do not have numerous, high-quality options for online grocery shopping, so the data for such countries is naturally low-quality.
- Currently, we include the following countries: Australia, Canada, China, India, Indonesia, Japan, Malaysia, Mexico, Pakistan, Philippines, South Africa, Spain, Thailand, Turkey, and the United States. We aimed to include Nigeria but were unsuccessful.
- Products are assigned to categories (barn, free-range, cage, and so on) automatically using the large language model Gemini. We manually check this classification, but errors may still occur. Errors will be obvious in the raw data (above), as the raw data contains the original product names.
- We began collecting data in 2025-06 (June), and we aim to collect data approximately every six months. Once a couple of years have passed, and we begin to see changes in the data over time, we will provide visualisations of these trends.
- In some countries, we have volunteers who generously visited key supermarkets in person and photographed all fresh egg products available for sale (a grateful shout-out to the Aijun Yang family!). We treat these the same in our data, except that we note that the data is from an in-person visit in the supermarket name, and we show the large language model the entire photo rather than just the product name.  

# Is the cage-free product share a good measure of the cage-free market share?
- No and yes.
- There are 15 countries listed above. 11 of those countries also have a cage-free market share estimated for the country as a whole for [Welfare Footprint Project](https://welfarefootprint.org/laying-hens/).
- If you take the mean product share estimated by me above ($$x$$), and then use that to perform a simple linear regression analysis predict the Welfare Footprint market share ($$y$$), you get a model like:

$$y = 0.33x$$

$$R^2 = 0.42, p = 0.0184$$

- Welfare Footprint's country-wide cage-free estimate is approximately one-third the magnitude of our product cage-free estimates from above. This makes total sense—we would expect cage-free eggs to be overrepresented in supermarkets' shell egg sections, as these products are most visible to consumers. We would expect caged eggs to be more commonly used for industrial food preparation, food service, and so on.
- The product share on this website predicts about 42% of the variance in Welfare Footprint's country-wide cage-free estimate. Despite the small sample size (n = 11), this relationship is statistically significant at the 0.05 level.
- So, if we don't have any data for a country's cage-free egg market, it would be reasonable to use one-third of the percentage of shell egg products that are cage-free in that country's main supermarkets.
