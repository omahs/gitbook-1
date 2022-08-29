# Ethereum Events Emitted Table

Native [Ethereum Events](https://docs.soliditylang.org/en/v0.7.5/contracts.html#events) exist within the `ethereum` schema, as `ethereum.events_emitted`&#x20;

Notable Features:

* All event inputs are decoded and stored in a fully queryable JSON column called `event_inputs`
* Flipside's labels have been merged in.
* Every contract has an associated name that corresponds 1:1 with the solidity contract code.

## Table Schema

`ethereum.events_emitted`

| Field                    | Type      | Description                                                                                                    |
| ------------------------ | --------- | -------------------------------------------------------------------------------------------------------------- |
| block\_id                | number    | The block height this event was recorded at.                                                                   |
| block\_timestamp         | timestamp | UTC block timestamp for parent block                                                                           |
| contract\_address        | address   | The parent contract that is responsible for kicking off this event.                                            |
| contract\_name           | string    | The name of this contract.                                                                                     |
| event\_index             | string    | The index/order of the event in the transaction                                                                |
| event\_inputs            | json      | Decoded event inputs (specifically topics/data are decoded)                                                    |
| event\_name              | string    | English decoded name for the event name. This could be a transfer, or any decoded log method or log event name |
| tx\_from\_address        | address   | The initiator of the transaction.                                                                              |
| tx\_from\_address\_name  | string    | [(see Labels section for details)](../../data-models/labels/)                                                  |
| tx\_from\_label          | string    | [(see Labels section for details)](../../data-models/labels/)                                                  |
| tx\_from\_label\_subtype | string    | [(see Labels section for details)](../../data-models/labels/)                                                  |
| tx\_from\_label\_type    | string    | [(see Labels section for details)](../../data-models/labels/)                                                  |
| tx\_to\_address          | address   | The receiver of the transaction or initial contract being called                                               |
| tx\_to\_address\_name    | string    | [(see Labels section for details)](../../data-models/labels/)                                                  |
| tx\_to\_label            | string    | [(see Labels section for details)](../../data-models/labels/)                                                  |
| tx\_to\_label\_subtype   | string    | [(see Labels section for details)](../../data-models/labels/)                                                  |
| tx\_to\_label\_type      | string    | [(see Labels section for details)](../../data-models/labels/)                                                  |
| tx\_id                   | string    | Transaction hash                                                                                               |
| tx\_succeeded            | string    | Was this transaction successful?                                                                               |
