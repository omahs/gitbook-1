# Solana Fact Proposal Votes

`solana.fact_proposal_votes`

| Field                | Type      | Description                                                                             |
| -------------------- | --------- | --------------------------------------------------------------------------------------- |
| governance\_platform | string    | Platform that is used for hosting the governance space. Either Realms or Tribeca.       |
| program\_name        | string    | Name or ID of the program where the voting took place                                   |
| block\_timestamp     | timestamp | The time the block began                                                                |
| block\_id            | integer   | Unique sequential number that identifies the current block                              |
| tx\_id               | string    | A unique key that identifies a transaction                                              |
| succeeded            | boolean   | TRUE when transaction succeeded. Otherwise this column is FALSE                         |
| voter                | string    | Digital signature corresponding to the public key of the account voting on the proposal |
| voter\_account       | string    | Account with locked tokens linked to the NFT (determines voting power)                  |
| voter\_nft           | string    | NFT mint used in this vote                                                              |
| proposal             | string    | Address representing the proposal being voted on                                        |

**Note**: This table only applies to Marinade proposals.
