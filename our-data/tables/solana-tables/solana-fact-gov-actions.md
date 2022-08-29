# Solana Fact Gov Actions

`solana.fact_gov_actions`

| Field            | Type      | Description                                                                     |
| ---------------- | --------- | ------------------------------------------------------------------------------- |
| program\_name    | string    | Name of the program where the voting took place                                 |
| block\_timestamp | timestamp | The time the block began                                                        |
| block\_id        | integer   | Unique sequential number that identifies the current block                      |
| tx\_id           | string    | A unique key that identifies a transaction                                      |
| succeeded        | boolean   | TRUE when transaction succeeded. Otherwise this column is FALSE                 |
| signer           | string    | Digital signature corresponding to the public key of the account                |
| locker\_account  | string    | Address corresponding to the account of the locker                              |
| mint             | string    | String that gives information about the token locked. Always Saber in this case |
| action           | string    | The governance action that is occuring                                          |
| amount           | float     | The amount of Saber                                                             |

**Note**: This table only applies to Saber and Marinade governance.
