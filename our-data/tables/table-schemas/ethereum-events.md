# Ethereum UDM Events Table

{% hint style="warning" %}
These legacy Ethereum tables are deprecated. See [Ethereum Core](../ethereum-core-tables.md) for up-to-date Ethereum models.
{% endhint %}

Ethereum events exist within the `ethereum` schema, as `ethereum.udm_events`&#x20;

Within the event table, native ETH transfers, internal transactions, and contract calls are all modeled as "events".

Notable Features that make querying simple:

* "Origin" metadata is carried down to every event. This is particularly useful if you want to query an event in the context of a specific origin contract call, i.e. all "burn" events that occur in the context of a token "transfer".
* All function names, log methods, and log events have been decoded into their human-readable format.
* All amounts have been decimal adjusted.
* All amounts, where applicable, contain their USD Equivalent.

## Table Schema

`ethereum.udm_events`

| Field                       | Type      | Description                                                                                                                                              |
| --------------------------- | --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| amount                      | number    | Native amount of transfer (decimal adjusted)                                                                                                             |
| amount\_usd                 | number    | In the case of a transfer event, the equivalent amount in USD. Note this is computed by taking the average hourly price around the time of the tx event. |
| block\_number               | number    | The block height this event was recorded at.                                                                                                             |
| block\_timestamp            | timestamp | UTC block timestamp for parent block                                                                                                                     |
| contract\_address           | address   | The parent contract that is responsible for kicking off this event.                                                                                      |
| event\_id                   | string    | The index/order of the event in the transaction                                                                                                          |
| event\_name                 | string    | English decoded name for the event name. This could be a transfer, or any decoded log method or log event name                                           |
| event\_type                 | string    | The english name for the type of event. This could be a native eth event, erc20 transfer, or contract methods calls/events.                              |
| from\_address               | address   | The sender of the event                                                                                                                                  |
| from\_address\_name         | string    | [(see Labels section for details)](../../data-models/labels/)                                                                                            |
| from\_label                 | string    | [(see Labels section for details)](../../data-models/labels/)                                                                                            |
| from\_label\_subtype        | string    | [(see Labels section for details)](../../data-models/labels/)                                                                                            |
| from\_label\_type           | string    | [(see Labels section for details)](../../data-models/labels/)                                                                                            |
| origin\_address             | address   | The initiator of the transaction                                                                                                                         |
| origin\_address\_name       | string    | [(see Labels section for details)](../../data-models/labels/)                                                                                            |
| origin\_function\_name      | string    | Input function signature decoded to English name for the parent tx that kicked off this event, if applicable                                             |
| origin\_function\_signature | string    | The function signature of contract call, if applicable                                                                                                   |
| origin\_label               | string    | [(see Labels section for details)](../../data-models/labels/)                                                                                            |
| origin\_label\_subtype      | string    | [(see Labels section for details)](../../data-models/labels/)                                                                                            |
| origin\_label\_type         | string    | [(see Labels section for details)](../../data-models/labels/)                                                                                            |
| symbol                      | string    | The symbol for the contract, if applicable.                                                                                                              |
| to\_address                 | address   | The receiver of the transaction or contract being called                                                                                                 |
| to\_address\_name           | string    | [(see Labels section for details)](../../data-models/labels/)                                                                                            |
| to\_label                   | string    | [(see Labels section for details)](../../data-models/labels/)                                                                                            |
| to\_label\_subtype          | string    | [(see Labels section for details)](../../data-models/labels/)                                                                                            |
| to\_label\_type             | string    | [(see Labels section for details)](../../data-models/labels/)                                                                                            |
| tx\_id                      | string    | Transaction id for this transfer                                                                                                                         |



