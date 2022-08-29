# Solana Fact NFT Sales

`solana.fact_nft_sales`

| Field            | Type      | Description                                                                             |
| ---------------- | --------- | --------------------------------------------------------------------------------------- |
| block\_timestamp | timestamp | The time the block began                                                                |
| block\_id        | integer   | Unique sequential number that identifies the current block                              |
| tx\_id           | string    | A unique key that identifies a transaction                                              |
| succeeded        | boolean   | TRUE when transaction succeeded. Otherwise this column is FALSE                         |
| program\_id      | string    | An address that corresponds to the contract being interacted with during the NFT sale.  |
| purchaser        | string    | The wallet address of the individual who bought the NFT                                 |
| mint             | string    | Identifier for the NFT being minted or purchased on the secondary market                |
| sales\_amount    | string    | The amount the NFT was purchased for in Solana                                          |

This table includes data for NFT purchases on the secondary marketplaces. Currently, the table includes data for Magic Eden, Solanart, Solport, and the Solana Monkey Business marketplace.&#x20;
