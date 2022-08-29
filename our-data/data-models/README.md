---
description: >-
  The Data Models section provides an overview of Flipside's cross-chain
  blockchain data schemas.
---

# Data Model Overview

Flipside's on-chain data is organized around a common set of data models. These common models provide a standard interface that makes it simple to perform analysis across a variety of blockchains without having to learn a new schema each time.&#x20;

To date, Flipside has parsed over 60+ blockchains leveraging our Chainwalking technology. For each blockchain parsed, data is cleaned and normalized into the following models:

1. **Events** - events represent the distillation of all interactions that occur within a transaction. For example, transfers, rewards, staking, internal transactions, smart contract calls, etc.
2. **Address Balances** - balance readings are taken each time an address is involved in a transaction.

All tables are enriched with [Flipsides Labels](labels/).&#x20;

Let's start by exploring Flipside's [event model](events-data-model.md).&#x20;

{% content-ref url="events-data-model.md" %}
[events-data-model.md](events-data-model.md)
{% endcontent-ref %}

