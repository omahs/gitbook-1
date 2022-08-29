# Solana Fact Gauges Votes

`solana.fact_gauges_votes`

| Field             | Type      | Description                                                                            |
| ----------------- | --------- | -------------------------------------------------------------------------------------- |
| program\_name     | string    | Name of the program where the voting took place                                        |
| block\_timestamp  | timestamp | The time the block began                                                               |
| block\_id         | integer   | Unique sequential number that identifies the current block                             |
| tx\_id            | string    | A unique key that identifies a transaction                                             |
| succeeded         | boolean   | TRUE when transaction succeeded. Otherwise this column is FALSE                        |
| voter             | string    | Address corresponding to the voter wallet                                              |
| gauge             | string    | Gauges allow voting escrows to allocate the rewards of a set of liquidity mining pools |
| power             | integer   | The percentage of their personal voting power a voter delegates to a gauge             |
| delegated\_shares | integer   | Amount of Saber the voter has delegated                                                |

**Note:** This table only applies to Saber gauges.&#x20;
