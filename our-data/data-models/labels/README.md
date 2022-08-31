# Labels

Labels identify known addresses that are associated with a CEX, DEX, NFT project, liquidity pool, or other entity. Each known address receives only one label, and that label is considered a "source of truth" for that address. Not every address has a label.&#x20;

See [the Crosschain schema](../../tables/crosschain-tables/crosschain-address-labels.md) for a table containing all labeled addresses.&#x20;

Flipside applies a 2-level hierarchy to all labeled addresses using 4 field attributes.&#x20;



![](<../../../.gitbook/assets/Velocity Documentation - Labels.png>)

| creator               | Name of the creator of the label                                                                |
| --------------------- | ----------------------------------------------------------------------------------------------- |
| label\_type           | A high-level category describing the addresses main function or ownership (e.g. exchange)       |
| label\_subtype        | A sub-category nested within label type providing further detail (e.g. exchange deposit wallet) |
| project\_name (label) | The name of the entity that controls the address (e.g. Binance).                                |
| address\_name         | A description of the use of the address by the controlling entity (e.g. Binance deposit wallet) |

Note: on Event and Balance tables there is no need to join a secondary table to group or filter by label attributes .

{% hint style="info" %}
Events and Balance tables are automatically enriched with label columns corresponding to any column that contains an address type. The pattern for these columns names is: `{address_function}_{label_attribute}`
{% endhint %}

For example, in an events table, the following columns would be present to account for labels on the `event_from` . These would also exist for `event_to`, `tx_from`,`tx_to`, etc.

```
event_from_label_type
event_from_label_subtype
event_from_label
event_from_address_name
```

## Label Types

There are 10 label types within any blockchain.

1. ****[**cex** (Centralized Exchange)](cex-label-type.md)
2. ****[**dex** (Decentralized Exchange)](dex-label-type.md)
3. ****[**operator** (Chain Operations)](operator-label-type.md)
4. ****[**chadmin** (Chain Administration)](chadmin-label-type.md)
5. ****[**defi** (Decentralized Finance Applications)](dex-label-type.md)
6. ****[**nft** (NonFungible Token Contracts & Applications)](nft-label-type.md)
7. ****[**layer2** (Layer 2 Dapps)](layer2-label-type.md)
8. ****[**dapp** (Decentralized Applications)](other-label-type.md)
9. ****[**token** (Token Contracts)](token-label-type.md)
10. ****[**flotsam** (Junk or Other)](flotsam-label-type.md)

