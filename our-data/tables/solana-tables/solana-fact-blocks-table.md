# Solana Fact Blocks Table

### Table Schema

`solana.fact_blocks`

| Field                 | Type      | Description                                                                         |
| --------------------- | --------- | ----------------------------------------------------------------------------------- |
| block\_id             | integer   | Unique sequential number that identifies the current block                          |
| block\_timestamp      | timestamp | The time the block began                                                            |
| network               | string    | Mainnet or testnet                                                                  |
| chain\_id             | string    | Cross-chain identifier                                                              |
| tx\_count             | integer   | Number of actions (inclusive of votes, etc) that occured during that block          |
| block\_height         | integer   | Number of blocks beneath the current block, the first block after the genesis block |
| block\_hash           | integer   | Unique value that identifies the block                                              |
| previous\_block_\__id | integer   | Block\_id that identifies the previous block                                        |
| previous\_block\_hash | string    | Identifies previous block                                                           |

**Notes:**

* `block_id` column in our data models matches what [Solcan](https://solscan.io/) classifies as `Block`. This value is same as what is referred to as `Slot`.
* While blocks are sequential in number, some blocks do not contain any transactions. Blocks that do not contain transactions are not included in this table.&#x20;
