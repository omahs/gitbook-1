---
description: uniswapv3.lp_actions
---

# LP Actions

Use this table to track increases and decreases to positions by liquidity providers (LPs) over time. Whenever a Pool `Burn` or `Mint` event is triggered on a position a record is appended to this table.

| Field                         | Type      | Description                                                                                |
| ----------------------------- | --------- | ------------------------------------------------------------------------------------------ |
| `block_id`                    | number    | The block number that this lp action was recorded                                          |
| `block_timestamp`             | timestamp | The block timestamp that this lp action was recorded                                       |
| `tx_id`                       | text      | The transaction that contained this lp action                                              |
| `blockchain`                  | text      | The blockchain this lp action was created on (Ethereum, will support L2s here shortly)     |
| `pool_address`                | address   | The contract address of the pool                                                           |
| `pool_name`                   | text      | The name of the Pool (format = "{token0}-{token1} {tick\_spacing} {fee}")                  |
| `action`                      | text      | The type of lp action, either `INCREASE_LIQUIDITY` (mint) or `DECREASE_LIQUIDITY` (burn)   |
| `liquidity_adjusted`          | number    | The amount of liquidity to mint or burn, decimal adjusted.                                 |
| `liquidity_provider`          | address   | The address of the liquidity provider                                                      |
| `nf_position_manager_address` | address   | The address of the peripheral nf position manager contract, if used.                       |
| `nf_token_id`                 | number    | The id of the NFT associated with the liquidity position                                   |
| `price_lower_0_1`             | number    | Lower bound of the liquidity position represented as token 0 per token 1                   |
| `price_upper_0_1`             | number    | Upper bound of the liquidity position represented as token 0 per token 1                   |
| `price_lower_0_1_usd`         | number    | Lower bound of the liquidity position represented as token 0 per token 1, converted to USD |
| `price_upper_0_1_usd`         | number    | Upper bound of the liquidity position represented as token 0 per token 1, converted to USD |
| `price_lower_1_0`             | number    | Lower bound of the liquidity position represented as token 1 per token 0                   |
| `price_upper_1_0`             | number    | Upper bound of the liquidity position represented as token 1 per token 0                   |
| `price_lower_1_0_usd`         | number    | Lower bound of the liquidity position represented as token 1 per token 0, converted to USD |
| `price_upper_1_0_usd`         | number    | Upper bound of the liquidity position represented as token 1 per token 0, converted to USD |
| `tick_lower`                  | number    | Lower tick of the liquidity position                                                       |
| `tick_upper`                  | number    | Upper tick of the liquidity position                                                       |
| `token_0_address`             | address   | Contract address of token 0                                                                |
| `token_0_symbol`              | text      | Symbol of token 0                                                                          |
| `token_1_address`             | address   | Contract address of token 1                                                                |
| `token_1_symbol`              | text      | Symbol of token 1                                                                          |
