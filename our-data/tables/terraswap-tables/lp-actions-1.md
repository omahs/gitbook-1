---
description: terraswap.pool_reserves
---

# Terraswap Pool Reserves

This table provides block by block pool reserve information including total pool shares, pool currencies, and token amounts in Terraswap pools.&#x20;

| Field              | Type      | Description                                                                          |
| ------------------ | --------- | ------------------------------------------------------------------------------------ |
| `blockchain`       | text      | The blockchain this pool was created on.                                             |
| `chain_id`         | text      | ID of blockchain to connect to, it can be _columbus-3, columbus-4, columbus-5, etc._ |
| `block_id`         | number    | The block number that this pool reserve was recorded                                 |
| `block_timestamp`  | timestamp | The block timestamp that this pool reserve was recorded                              |
| `contract_address` | address   | The address of the liquidity pool                                                    |
| `total_share`      | number    | The total amount of shares  in a pool                                                |
| `token_0_currency` | text      | Token 0 currency                                                                     |
| `token_0_amount`   | number    | Token 0 amount in pool                                                               |
| `token_1_currency` | text      | Token 1 currency                                                                     |
| `token_1_amount`   | number    | Token 1 amount in pool                                                               |
