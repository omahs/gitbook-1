---
description: terraswap.lp_actions
---

# Terraswap LP Actions

Use this table to track liquidity provided or withdrawn by liquidity providers (LPs) on Terraswap. When an LP provides or withdraws liquidity from a Terraswap pool, the transaction is appended to this table.&#x20;

| Field                | Type      | Description                                                                            |
| -------------------- | --------- | -------------------------------------------------------------------------------------- |
| `blockchain`         | text      | The blockchain this lp action was created on.                                          |
| `chain_id`           | text      | ID of blockchain to connect to, it can be _columbus-3, columbus-4, columbus-5, etc._   |
| `block_id`           | number    | The block number that this lp action was recorded                                      |
| `block_timestamp`    | timestamp | The block timestamp that this lp action was recorded                                   |
| `tx_id`              | text      | The transaction that contained this lp action                                          |
| `event_type`         | text      | The type of lp action, either `PROVIDE_LIQUIDITY` (mint) or `WITHDRAW_LIQUIDITY`(burn) |
| `sender`             | address   | The address of the liquidity provider                                                  |
| `token_0_amount`     | number    | Token 0 amount in event                                                                |
| `token_0_amount_usd` | number    | Token 0 amount, converted to USD                                                       |
| `token_0_currency`   | text      | Token 0 currency                                                                       |
| `token_1_amount`     | number    | Token 1 amount in event                                                                |
| `token_1_amount_usd` | number    | Token 1 amount, converted to USD                                                       |
| `token_1_currency`   | text      | Token 1 currency                                                                       |
| `pool_address`       | address   | The contract address of the pool                                                       |
| `pool_name`          | text      | The name of the Pool                                                                   |
| `LP_share_amount`    | number    | The total amount of shares provided or withdrawn in a transaction                      |
| `LP_pool_address`    | address   | The address of the LP token issued                                                     |
| `LP_pool_name`       | text      | The name of the LP token issued                                                        |
