---
description: >-
  Terra transfer events, curated from Terra msg_events. Includes event_type
  transfers, cw20 token transfers, Wormhole transfers, and Delegator rewards
  transfers
---

# Transfer Events

## Table Schema

table name: `terra.transfer_events`

| Field                     | Type      | Description                                                                                                                                             |
| ------------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `BLOCK_TIMESTAMP`         | timestamp | The timestamp this block was recorded                                                                                                                   |
| `TX_ID`                   | text      | The transaction that contained this transfer                                                                                                            |
| `MSG_INDEX`               | number    | Message index, it is like the different steps for message, one message group can contain multiple message index values to deliver different information |
| `ACTION_INDEX`            | number    | Index for transfer event actions                                                                                                                        |
| `INITIAL_ACTION`          | text      | Initial action for a transfer event                                                                                                                     |
| `CURRENT_ACTION`          | text      | Current action for a transfer event                                                                                                                     |
| `SENDER`                  | text      | Transfer sender                                                                                                                                         |
| `SENDER_LABEL_TYPE`       | text      | [(see Labels section for details)](../../../address-tags-and-labels/labels/)                                                                            |
| `SENDER_LABEL_SUBTYPE`    | text      | [(see Labels section for details)](../../../address-tags-and-labels/labels/)                                                                            |
| `SENDER_ADDRESS_LABEL`    | text      | [(see Labels section for details)](../../../address-tags-and-labels/labels/)                                                                            |
| `SENDER_ADDRESS_NAME`     | text      | [(see Labels section for details)](../../../address-tags-and-labels/labels/)                                                                            |
| `RECIPIENT`               | text      | Transfer recipient                                                                                                                                      |
| `RECIPIENT_LABEL_TYPE`    | text      | [(see Labels section for details)](../../../address-tags-and-labels/labels/)                                                                            |
| `RECIPIENT_LABEL_SUBTYPE` | text      | [(see Labels section for details)](../../../address-tags-and-labels/labels/)                                                                            |
| `RECIPIENT_ADDRESS_LABEL` | text      | [(see Labels section for details)](../../../address-tags-and-labels/labels/)                                                                            |
| `RECIPIENT_ADDRESS_NAME`  | text      | [(see Labels section for details)](../../../address-tags-and-labels/labels/)                                                                            |
| `CURRENCY`                | text      | The transfer currency                                                                                                                                   |
| `AMOUNT`                  | number    | The transfer amount                                                                                                                                     |
| `AMOUNT_USD`              | number    | The transfer amount in USD, it is calculated by the hourly price multiplied by the transfer amount                                                      |
| `MSG_SENDER`              | text      | The message sender, from message event types                                                                                                            |
| `CONTRACT_ADDRESS`        | text      | The contract address that is responsible for kicking off the transfer event, if applicable                                                              |
| `CONTRACT_LABEL`          | text      | [(see Labels section for details)](../../../address-tags-and-labels/labels/)                                                                            |
