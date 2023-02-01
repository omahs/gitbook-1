---
description: >-
  How we design our data structures for accessibility and performance using the
  Star Schema approach.
---

# Data Modeling Approach

### Our Data Modeling Approach

Flipside models on-chain data around a common set of principles known as the [star schema](https://en.wikipedia.org/wiki/Star\_schema), an industry-standard model for relational data warehouses.&#x20;

A star schema is a data modeling technique commonly used in data warehousing and business intelligence to organize and represent data in a way that is easily accessible and understandable for end-users. The schema consists of a central fact table surrounded by dimension tables that provide additional context to the data in the fact table. The star schema design helps users quickly and easily analyze data by:

* reducing the complexity of the data structure
* enabling clear and meaningful data visualization
* improving query performance

This approach requires modelers to classify their tables as either **dimension** or **fact** tables.

_**Fact tables**_ store observations or events, and can be blocks, transactions, mints, swaps, etc. If you were modeling sales for a restaurant chain, for example, each sale might be represented by a row in a fact table.

_**Dimension ("dim") tables**_ describe entities—the things you analyze. Entities can include labels, prices, decimals, tags, etc. Extending the restaurant metaphor: if each individual sale is a fact, then which restaurant the sale occurred in would be a dimension, describing that fact.

The key here is that:

* _**Facts**_ support summarization ("what is the total number of sales?")
* _**Dimensions**_ support filtering and grouping ("what are the sales totals grouped by restaurant?")

This kind of schema design is incredibly popular, and we see it as a key part of our strategy to provide the most accessible and performant blockchain data possible.
