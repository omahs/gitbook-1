---
description: >-
  Row based event actions table curated from terra.msg_events event attributes.
  Actions or methods in the 'from_contract' event type are displayed as records
  based on contract address.
---

# Event Actions

## Table Schema

table name: `terra.event_actions`

| Field                     | Type      | Description                                                                                                                                             |
| ------------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `BLOCK_ID`                | number    | The block number for this event action                                                                                                                  |
| `BLOCK_TIMESTAMP`         | timestamp | The timestamp this block was recorded                                                                                                                   |
| `BLOCKCHAIN`              | text      | The blockchain name for this block                                                                                                                      |
| `CHAIN_ID`                | text      | ID of blockchain to connect to, it can be _columbus-3, columbus-4_, _columbus-5_, etc.                                                                  |
| `TX_ID`                   | text      | The transaction that contained this event action                                                                                                        |
| `ACTION_INDEX`            | number    | Index for event actions                                                                                                                                 |
| `MSG_INDEX`               | number    | Message index, it is like the different steps for message, one message group can contain multiple message index values to deliver different information |
| `ACTION_CONTRACT_ADDRESS` | text      | Contract address that kicked off this event action                                                                                                      |
| `CONTRACT_LABEL`          | text      | [(see Labels section for details)](../../../address-tags-and-labels/labels/)                                                                            |
| `ACTION_METHOD`           | text      | The action or method within an event                                                                                                                    |
| `ACTION_LOG`              | object    | The log that provides detail (amounts, to, from, etc.) to an action or method                                                                           |
