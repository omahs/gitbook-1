# Solana Fact Swaps

`solana.fact_swaps`

| Field                | Type      | Description                                                     |
| -------------------- | --------- | --------------------------------------------------------------- |
| swap\_program        | string    | The DEX or program used to make the swap                        |
| block\_timestamp     | timestamp | The time the block began                                        |
| block\_id            | integer   | Unique sequential number that identifies the current block      |
| tx\_id               | string    | A unique key that identifies a transaction                      |
| succeeded            | boolean   | TRUE when transaction succeeded. Otherwise this column is FALSE |
| swapper              | string    | Address that initiated the swap                                 |
| swap\_from_\__amount | integer   | Total amount of the token sent in to initiate the swap          |
| swap\_from_\__mint   | string    | Token being sent or swapped from                                |
| swap\_to_\__amount   | integer   | Total amount of the token received in the swap                  |
| swap\_to_\__mint     | string    | Token being received or swapped for                             |

Currently the swaps table only contains swap transactions completed on the Jupiter Aggregator and Orca Swaps. Coverage of swaps is estimated to be 95-98%. Swaps completed on Serum and Raydium are in the works and will arrive soon.&#x20;

Swaps contained in this table are unique on `block_id` and `transaction_id`. Additional SQL logic to find distinct entries or to dedupe the table is unnecessary.&#x20;
