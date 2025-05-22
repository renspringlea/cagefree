---
layout: home
---

This website presents, in a format convenient for decision-makers and funders working on caged hen welfare, key data relating to cage-free and caged eggs sold by supermarkets and retailers around the world. Data is updated every month or so.

The purpose of this data is to provide an additional source of information about how many egg products are cage-free as opposed to cage, especially for companies that do not have cage-free commitments or do not report on their commitment.
- Specifically, this website aims to present data on **the numbers of cage-free vs caged shell egg products sold by retailers in specific countries**.
- This website does *not* include data on sales numbers—rather, the data collects details about products that are available for purchase at major retailers in the specific countries, and whether those products are caged or cage-free.
- We only include grocery retailers, such as supermarkets and hypermarkets. We do not include restaurants, food service businesses, and so on.
- Data is systematically scraped from online supermarket websites. For each country, we have aimed to include all of the major supermarkets in this country. However, this is not always possible; countries like Japan have a very decentralised retail industry, so it is not possible to achieve wide market coverage in those countries. Likewise, some countries simply do not have numerous, high-quality options for online grocery shopping, so the data for such countries is naturally low-quality.
- Currently, we include the following countries: China, India, Indonesia, United States, Mexico, Philippines,
Australia, Canada, India, Indonesia, Japan, Malaysia, Mexico, Nigeria, Pakistan, Philippines, South Africa, Spain, Thailand, Turkey, United States. We aimed to include China but were unsuccessful.
- We began collecting data in 2025-05 (May), and we aim to collect data every month or so. Once a couple of years have passed, and we begin to see trends in the data over time, we will also provide visualisations of how the numbers of products are changing over time.

# Numbers of products by country and retail chain
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

# Raw data for download
For your own analysis, you may download:
- [The aggregate table](_data/aggregate_table_alltime.csv) - this is the same table as shown above, though there is one table for every month since we began collecting data. This lets you see how numbers are changing over time.
- [The raw table](_data/raw_table_alltime.csv) - this is the name and details corresponding to every individual egg product. The raw table is the original data underlying the aggregate table (above).
