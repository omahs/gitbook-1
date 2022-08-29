# Solana Fact Transfers Table

### Table Schema

`solana.fact_transfers`

| Field            | Type      | Description                                                                       |
| ---------------- | --------- | --------------------------------------------------------------------------------- |
| block\_timestamp | timestamp | The time the block began                                                          |
| block\_id        | integer   | Unique sequential number that identifies the current block                        |
| tx\_id           | string    | A unique key that identifies a transaction.                                       |
| index            | integer   | Number corresponding to location within a transaction of where the event occurred |
| tx\_from         | string    | Wallet address of entity initializing the transaction                             |
| tx\_to           | string    | Wallet address of entity receiving a transaction                                  |
| amount           | integer   | Amount of Solana or other currency being transacted.                              |
| mint             | string    | Identifier for the token or NFT being transferred between wallets                 |

Transfers contained in this table are unique on `block_id` and `transaction_id`. Additional SQL logic to find distinct entries or to dedupe the table is unnecessary.&#x20;
