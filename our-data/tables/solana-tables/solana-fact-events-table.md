# Solana Fact Events Table

### Table Schema

`solana.fact_events`

| Field              | Type      | Description                                                                                                                                                         |
| ------------------ | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| block\_timestamp   | timestamp | The time the block began                                                                                                                                            |
| block\_id          | integer   | Unique sequential number that identifies the current block                                                                                                          |
| tx\_id             | string    | A unique key that identifies a transaction.                                                                                                                         |
| index              | integer   | Location of the event within the instructions of a transaction                                                                                                      |
| event\_type        | string    | The type of event (i.e. "transfer", "createAccount") that is occurring                                                                                              |
| program\_id        | string    | An address that corresponds to the contract being interacted with during the event                                                                                  |
| instruction        | json      | An instruction specifies which program it is calling, which accounts it wants to read or modify, and additional data that serves as auxiliary input to the program. |
| inner\_instruction | json      | A call from one smart contract program to another.                                                                                                                  |

**Note:** A singular transaction can contain multiple events. The `index` field allows one to determine where the event occurred within the transaction. ****&#x20;
