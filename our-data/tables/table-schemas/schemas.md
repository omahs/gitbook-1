# Ethereum Transactions Table

Ethereum transactions exist within the `ethereum` schema, as `ethereum.transactions` .

Transactions contain top-level summary information not found in `ethereum.udm_events`, for example, transaction fees and gas.

### How are transactions modeled along-side events?

**Case #1: Native Eth Transfer (no contracts called)**

If Person A, sent 5 ETH to PersonB, this would results in 1 record in the transactions table, and 1 event in `ethereum.udm_events` to record the "transfer" event.

**Case #2: ERC-20 Transfer (contract call)**

If Person A, sent 10 USDC to Person B, this would result in 1 record in `ethereum.transactions` , and 1 event in `ethereum.udm_events` to record the "transfer" event.

In cases where more complex contract methods are called, multiple events are recorded in the event table with a reference back to the transaction.

## Table Schema

`ethereum.transactions`

| Field                | Type                               | Description                                                         |
| -------------------- | ---------------------------------- | ------------------------------------------------------------------- |
| block\_number        | number                             | The block height this event was recorded at.                        |
| block\_timestamp     | timestamp                          | UTC block timestamp for parent block                                |
| event\_count         | number                             | The number of events contained within this transaction.             |
| fee                  | number                             | The transaction fee calculated from the gas price and the gas used. |
| fee\_usd             | number                             | The USD equivalent fee at the time of the transaction.              |
| from\_address        | address                            | The sender/initiator of the transaction.                            |
| from\_addres\_name   | [label](../../data-models/labels/) | [(see label's data model for details)](../../data-models/labels/)   |
| from\_label          | [label](../../data-models/labels/) | [(see label's data model for details)](../../data-models/labels/)   |
| from\_label\_subtype | [label](../../data-models/labels/) | [(see label's data model for details)](../../data-models/labels/)   |
| from\_label\_type    | [label](../../data-models/labels/) | [(see label's data model for details)](../../data-models/labels/)   |
| function\_name       | string                             | The English decoded name of the function signature, if applicable.  |
| function\_signature  | string                             | The function signature of the contract call, if applicable.         |
| gas\_limit           | number                             | The gas limit specified in this transaction.                        |
| gas\_price           | number                             | The gas price at the time of this transaction.                      |
| gas\_used            | number                             | The amount of gas used by this transaction.                         |
| nonce                | number                             | The number of transactions sent from the `from_address.`            |
| success              | text                               | The success state of this transaction execution.                    |
| symbol               | text                               | The project symbol (i.e. ERC-20 transaction), if applicable.        |
| to\_address          | text                               | The recipient of the transaction, or contract being called.         |
| to\_addres\_name     | [label](../../data-models/labels/) | [(see label's data model for details)](../../data-models/labels/)   |
| to\_label            | [label](../../data-models/labels/) | [(see label's data model for details)](../../data-models/labels/)   |
| to\_label\_subtype   | [label](../../data-models/labels/) | [(see label's data model for details)](../../data-models/labels/)   |
| to\_label\_type      | [label](../../data-models/labels/) | [(see label's data model for details)](../../data-models/labels/)   |
| tx\_id               | string                             | The hash (unique identifier) of the transaction.                    |
| tx\_position         | string                             | The position of the transaction in the block.                       |

