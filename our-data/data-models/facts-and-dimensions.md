# Facts and Dimensions

What are facts and dimensions?

Facts and dimensions are a part of what is called a star schema. Star schema is a mature modeling approach widely adopted by relational data warehouses. It requires modelers to classify their model tables as either dimension or fact.

_**Fact tables**_ store observations or events, and can be blocks, transactions, mints, swaps, etc.

_**Dimension tables**_ describe entities—the things you analyze. Entities can include labels, prices, decimals, tags, etc

The key here is that:

* _**Dimensions**_ support filtering and grouping
* _**Facts**_ support summarization

This type of modeling is a logical design technique used to structure data so that it is intuitive to users and delivers fast query performance. What makes the star schema stand out is its simplicity and ability to be understood by users.

The schema works by dividing data into measurements and the “who, what, where, when, why, and how” descriptive context. Broadly, these two groups are facts and dimensions.

Lets do a crypto transaction for an example

* The amount you spent and how many items you bought would be considered a fact, but what exchange rate and what blockchain would be considered dimensions.
* Once these two groups have been established, we can connect them by the unique transaction number associated with your specific purchase.
