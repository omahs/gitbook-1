# Solana Dim Labels

`solana.dim_labels`

| Field          | Type   | Description                                                                                     |
| -------------- | ------ | ----------------------------------------------------------------------------------------------- |
| blockchain     | string | Cross-chain identifier. In this table, `blockchain` will always be Solana                       |
| creator        | string | Name of the creator of the label                                                                |
| address        | string | Address that the label is associated with.                                                      |
| label\_type    | string | A high-level category describing the addresses main function or ownership (eg exchange).        |
| label\_subtype | string | A sub-category nested within label type providing further detail (e.g. exchange deposit wallet) |
| label          | string | The name of the entity that controls the address (e.g. Binance)                                 |
| address\_name  | string | A description of the use of the address by the controlling entity (e.g. Binance deposit wallet) |

Labels contained in any Flipside `labels` table are unique on the following fields: `blockchain, address, creator`.  There are 10 different `label_type`s contained in this table, more information can be found in the [labels data model overview](../../data-models/labels/).&#x20;
