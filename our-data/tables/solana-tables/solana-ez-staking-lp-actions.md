# Solana EZ Staking LP Actions

### Table Schema

`solana.ez_staking_lp_actions`

| Field                  | Type      | Description                                                                               |
| ---------------------- | --------- | ----------------------------------------------------------------------------------------- |
| block\_id              | integer   | Slot for which a block can be created.                                                    |
| block\_timestamp       | timestamp | The date and time at which the block began.                                               |
| tx\_id                 | string    | A unique key that identifies a transaction.                                               |
| succeeded              | boolean   | True when a transaction is successful, otherwise false.                                   |
| index                  | integer   | Location of the event within the instructions of a transaction.                           |
| event\_type            | string    | The type of event (i.e. "delegate", "withdraw") that is occurring.                        |
| signers                | array     | List of accounts that signed the transaction.                                             |
| stake\_authority       | string    | The wallet address of the user who initialized the transaction.                           |
| withdraw\_authority    | string    | The wallet address of the user that is withdrawing the stake.                             |
| stake\_account         | string    | An account address containing balances of staked SOL that belongs to the stake authority. |
| stake\_active          | boolean   | Whether or not the stake is actively staked with the validator.                           |
| pre tx staked balance  | array     | The amount of Solana belonging to the stake account before the transaction.               |
| post tx staked balance | array     | The amount of Solana belonging to the stake account after the transaction.                |
| withdraw\_amount       | integer   | The amount of Solana withdrawn from the stake account.                                    |
| withdraw\_destination  | string    | The wallet that the SOL is being withdrawn to.                                            |
| vote\_account          | string    | A voting account belonging to the validator.                                              |
| node\_pubkey           | string    | A unique key belonging to the validator node.                                             |
| validator\_rank        | integer   | The rank of the validator by amount of delegated SOL.                                     |
| commission             | integer   | The percentage of staked earnings given to the validator.                                 |
| validator\_name        | string    | The name of the validator when available.                                                 |
