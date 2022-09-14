---
description: Free the data. Query where you work.
---

# Access Flipside Data



### Access

Our data is free and you can access it in your preferred environment.

#### Flipside Web App

Almost everyone uses the [Flipside web app](https://flipside.new), our in-browser SQL editor, to explore our data, create visualizations, and publish dashboards.

#### API/SDK

Developers, analysts, and data scientists use our [REST API with SDKs](https://docs.flipsidecrypto.com/shroomdk-sdk/sdks) for JavaScript, Python, and R, to access our data programmatically.

#### Data Shares

Teams who want to build in their own Snowflake environment use our [Snowflake Data Shares](../data-shares/snowflake-data-shares.md) to build with large datasets joined with their own internal data.



#### When should I use the Flipside web app?

Use the [Flipside web app](https://flipside.new) to explore our data, create visualizations, and publish dashboards. The app also supports parameterized queries for interactive dashboards.

The Flipside app is perfect for creating short or long form analyses for your own research, to solve analytics bounties (e.g. [Flipside bounties](https://flipsidecrypto.xyz/earn) or [MetricsDAO bounties](https://metricsdao.xyz/)), or to share your dashboards and insights with the world.

#### When should I use the API/SDK?

Use our [REST API with SDKs](https://docs.flipsidecrypto.com/shroomdk-sdk/sdks) when you want to build light-weight applications, analyze the results of your SQL with your preferred language, or build models and visualizations beyond the capabilities of the Flipside Web app.

You should _not_ use the API to attempt ongoing downloads of large datasets (e.g. to copy our data) or if you want to join Flipside data with your own data. There’s a better and more robust way to access all our data: Snowflake data shares (see below).

#### **When should I request a Snowflake data share?**

Request a [data share](../data-shares/snowflake-data-shares.md) when you want Snowflake access to the entirety of our petabyte scale databases in your own Snowflake environment. This is the best option for teams who want to incorporate large amounts of historical data, real-time data, or who want to join our data with their own internal data.

Access to Snowflake data shares is free, and you pay for your own Snowflake compute costs.



### What blockchains and projects does Flipside have data on?

If it happens on-chain, we've got it. We have related off-chain data, too.

Data include core tables (blocks, events, transactions) for every chain, with added 'easy' tables (swaps, prices, etc.) and project-specific tables modeled by the Flipside community.

| [Crosschain Tables (prices, address tags)](tables/crosschain-tables/) | [MakerDAO](tables/ethereum-maker-dao-tables.md)            |
| --------------------------------------------------------------------- | ---------------------------------------------------------- |
| [Arbitrum](tables/arbitrum-tables.md)                                 | [NEAR ](tables/near-tables.md)                             |
| [AAVE](tables/aave-tables/)                                           | [Optimism](tables/optimism-tables.md)                      |
| [Avalanche](tables/avalanche-tables.md)                               | [Osmosis](tables/osmosis-tables/)                          |
| [Algorand](tables/algorand-tables/)                                   | [Polygon (legacy tables)](tables/polygon-tables/)          |
| [Astroport](tables/astroport-tables/)                                 | [Polygon 2.0](tables/polygon-2.0-tables.md)                |
| [BSC](tables/bsc-tables.md)                                           | [Solana](tables/solana-tables.md)                          |
| [Compound](tables/compound-tables/)                                   | [Sushi](tables/ethereum-sushi-tables.md)                   |
| [Ethereum (legacy tables)](tables/table-schemas/)                     | [Terra](tables/terra-tables/)                              |
| [Ethereum Core](tables/ethereum-core-tables/)                         | [Terraswap](tables/terraswap-tables/)                      |
| [FLOW](tables/flow-tables/)                                           | [THORChain](tables/thorchain-tables/thorchain-base-table/) |
| [Gnosis](tables/flow-tables/)                                         | [Uniswap V3](tables/uniswap-v3-tables/)                    |

Want to dive deeper? Use the [Flipside web app](https://flipside.new) to explore a specific data schema, or use the search bar at the top of our [Discover](https://flipsidecrypto.xyz/discover/dashboards) page to see trending analyses.

