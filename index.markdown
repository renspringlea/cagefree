---
layout: home
---

This website presents, in a format convenient for decision-makers and funders working on caged hen welfare, key data relating to cage-free and caged eggs sold by supermarkets and retailers around the world. Data is updated every month or so.

Specifically, this website aims to present data on **the numbers of cage-free vs caged shell egg products sold by major grocery retailers in specific countries**. This website does *not* include data on sales numbers—rather, the data collects details about products that are available for purchase at major retailers in the specific countries, and whether those products are caged or cage-free.

The purpose of this data is to provide an additional source of information about how many egg products are cage-free as opposed to cage, especially for companies that do not have cage-free commitments or do not report on their commitment. This fills an important gap in our understanding of the cage-free egg market around the world, but this data has little meaning in isolation. Please interpret this data alongside other important publications:

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
  This table shows data for the most recent month during which data was collected. For historic data, see the downloads below.<br />
  The "organic" category is assumed to be cage free. This is usually true, but this might be false in some countries.<br />
  When calculating the percentage of products that are cage-free for a specific company, we assume that the "insufficient information" category represents caged eggs. This means that the cage-free percentage is a conservative estimate.<br />
  Whether a company has/is reporting on a cage-free commitment is our best guess, and we welcome any corrections.
</div>

# Raw/historic datasets  

For your own analysis, you may download the raw data:  

- [The aggregate table for this month](_data/aggregate_table_current.csv) - this is the table shown above, exactly as you see it.
- [The aggregate table for all time](_data/aggregate_table_alltime.csv) - this is the table as shown above, though there is one table for every month since we began collecting data. This lets you examine how numbers are changing over time.
- [The raw table for all time](_data/raw_table_alltime.csv) - this is the name and details corresponding to every individual egg product. The raw table is the original data underlying the aggregate table (above).

# About the data  
- We only include grocery retailers, such as supermarkets and hypermarkets. We do not include restaurants, food service businesses, and so on. We focus on shell eggs; some retailers include liquid or powered eggs in their online store pages under the "egg" category, and such instances are included in the data. However, where retailers include liquid or powered eggs under a separate category, we made no effort to obtain that data. We have done our best to remove eggs from animals other than chickens (e.g. quails), though we may have missed some.
- Data is systematically scraped from online supermarket websites. For each country, we have aimed to include all of the major supermarkets in this country. However, this is not always possible; countries like Japan have a very decentralised retail industry, so it is not possible to achieve wide market coverage in those countries. Likewise, some countries simply do not have numerous, high-quality options for online grocery shopping, so the data for such countries is naturally low-quality.
- Currently, we include the following countries: Australia, Canada, India, Indonesia, Japan, Malaysia, Mexico, Nigeria, Pakistan, Philippines, South Africa, Spain, Thailand, Turkey, and the United States. We aimed to include China but were unsuccessful.
- We began collecting data in 2025-05 (May), and we aim to collect data every month or so. Once a couple of years have passed, and we begin to see changes in the data over time, we will provide visualisations of these trends.
