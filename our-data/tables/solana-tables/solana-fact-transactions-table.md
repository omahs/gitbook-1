# Solana Fact Transactions Table

### Table Schema

`solana.fact_transactions`

| Field                 | Type      | Description                                                                                                                                                        |
| --------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| block\_timestamp      | timestamp | The time the block began                                                                                                                                           |
| block\_id             | integer   | Unique sequential number that identifies the current block                                                                                                         |
| tx\_id                | string    | A unique key that identifies a transaction.                                                                                                                        |
| recent\_block\_hash   | string    | A string that prevents duplication and gives lifetime transactions of the block.                                                                                   |
| signers               | array     | Digital signatures corresponding to the accounts' public keys                                                                                                      |
| fee                   | integer   | Transaction fee (in lamports)                                                                                                                                      |
| succeeded             | boolean   | TRUE when transaction succeeded. Otherwise this column is FALSE                                                                                                    |
| account\_keys         | array     | Addresses used to store state between transactions                                                                                                                 |
| pre\_balances         | array     | Contains Solana balances of the accounts before the event                                                                                                          |
| post\_balances        | array     | Contains Solana balances of accounts after the event                                                                                                               |
| pre\_token\_balances  | array     | Decoded spl-token details before the event occurred                                                                                                                |
| post\_token\_balances | array     | Decoded spl-token details after the event occurred                                                                                                                 |
| instructions          | json      | An instruction specifies which program it is calling, which accounts it wants to read or modify, and additional data that serves as auxiliary input to the program |
| inner\_instructions   | json      | Contained within the instructions. A call from one smart contract program to another                                                                               |
| log\_messages         | array     | A message contains a header, followed by a compact-array of account addresses, followed by a recent block hash, followed by a compact-array of instructions        |

This table contains a high level overview of all transactions on Solana that are not votes or the Pyth Oracle. This contains, but is not limited to, swaps, transfers, NFT mints, and staking actions.&#x20;

Transactions contained in this table are unique on `block_id` and `transaction_id`. Additional SQL logic to find distinct entries or to dedupe the table is unnecessary.&#x20;
