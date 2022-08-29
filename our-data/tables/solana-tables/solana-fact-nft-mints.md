# Solana Fact NFT Mints

`solana.fact_nft_mints`

| Field            | Type      | Description                                                                        |
| ---------------- | --------- | ---------------------------------------------------------------------------------- |
| block\_timestamp | timestamp | The time the block began                                                           |
| block\_id        | integer   | Unique sequential number that identifies the current block                         |
| tx\_id           | string    | A unique key that identifies a transaction                                         |
| succeeded        | boolean   | TRUE if the transaction was successful, otherwise FALSE                            |
| program\_id      | string    | An address that corresponds to the contract being interacted with during the event |
| purchaser        | string    | The wallet address of the individual who minted the NFT                            |
| mint\_price      | integer   | The price the NFT was minted for in Solana or other currency                       |
| mint\_currency   | string    | A string corresponding to the currency used to mint the NFT                        |
| mint             | string    | Identifier for the NFT being minted or purchased on the secondary market           |
