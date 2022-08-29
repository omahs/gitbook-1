# Solana Fact Staking/LP Actions

`solana.fact_staking_lp_actions`

| Field                 | Type      | Description                                                                                                                                                        |
| --------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| block\_timestamp      | timestamp | The time the block began                                                                                                                                           |
| block\_id             | integer   | Unique sequential number that identifies the current block                                                                                                         |
| tx\_id                | string    | A unique key that identifies a transaction                                                                                                                         |
| succeeded             | boolean   | TRUE when transaction succeeded. Otherwise this column is FALSE                                                                                                    |
| index                 | integer   | Number corresponding to location within a transaction of where the event occurred                                                                                  |
| event\_type           | string    | The type of event (i.e. "delegate", "withdraw") that is occurring                                                                                                  |
| program\_id           | string    | An address corresponding to the contract being interacted with during the event                                                                                    |
| signers               | array     | Digital signatures corresponding to the accounts' public keys                                                                                                      |
| account\_keys         | array     | Addresses used to store state between transactions                                                                                                                 |
| instruction           | json      | An instruction specifies which program it is calling, which accounts it wants to read or modify, and additional data that serves as auxiliary input to the program |
| inner\_instruction    | json      | Contained within the instructions. A call from one smart contract program to another.                                                                              |
| pre\_balances         | array     | Contains Solana balances of the accounts before the event                                                                                                          |
| post\_balances        | array     | Contains Solana balances of accounts after the event                                                                                                               |
| pre\_token\_balances  | json      | Decoded spl-token details before the event occurred                                                                                                                |
| post\_token\_balances | json      | Decoded spl-token details after the event occurred                                                                                                                 |
