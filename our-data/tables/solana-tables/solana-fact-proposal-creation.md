# Solana Fact Proposal Creation

### Table Schema

`solana.core.fact_proposal_creation`

| Field                | Type      | Description                                                                 |
| -------------------- | --------- | --------------------------------------------------------------------------- |
| governance\_platform | string    | The platform used for the governance space.                                 |
| program\_name        | string    | Name of the project the NFT token belongs to.                               |
| block\_timestamp     | timestamp | The date and time at which the block began.                                 |
| block\_id            | integer   | Slot for which a block can be created.                                      |
| tx\_id               | string    | A unique key that identifies a transaction.                                 |
| succeeded            | boolean   | True when a transaction is successful, otherwise false.                     |
| realms\_id           | string    | An address that is unique to the space or voting group on Realms.           |
| proposal             | string    | Address representing the proposal being voted on.                           |
| proposal\_writer     | string    | Address of the user who is submitting the proposal for voting.              |
| proposal\_name       | string    | The name of the proposal that is being submitted.                           |
| vote\_type           | string    | The type of voting strategy that will be used for voting on the proposal.   |
| vote\_options        | array     | The options that will be available to users who are voting on the proposal. |
