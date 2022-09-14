# ERC20 Balances Table

{% hint style="warning" %}
These legacy Ethereum tables are deprecated. See [Ethereum Core](../ethereum-core-tables/) for up-to-date Ethereum models.
{% endhint %}

The `ethereum.erc20_balances` table contains daily roll-ups of balances for each address associated with an ERC-20 token. The table is updated throughout the day, to provide an intra-day view of balance readings as on-chain events occur.&#x20;

## Table Schema

`ethereum.erc20_balances`

| Field             | Type                                           | Description                                                                                                                                |
| ----------------- | ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| address\_name     | [label](../../address-tags-and-labels/labels/) | [(see Labels section for details)](../../address-tags-and-labels/labels/)                                                                  |
| amount\_usd       | number                                         | USD Value of the token balance                                                                                                             |
| balance           | number                                         | Latest recorded balance for that given day and token.                                                                                      |
| balance\_date     | string                                         | UTC timestamp of the day the balance was recorded on.                                                                                      |
| contract\_address | address                                        | Token contract address.                                                                                                                    |
| contract\_label   | [label](../../address-tags-and-labels/labels/) | The label associated with the `contract_address`[(see Labels section for more details)](../../address-tags-and-labels/labels/).            |
| label             | [label](../../address-tags-and-labels/labels/) | The label associated with the `user_address`column [(see Labels section for more details)](../../address-tags-and-labels/labels/).         |
| label\_subtype    | [label](../../address-tags-and-labels/labels/) | The label subtype associated with the `user_address`column [(see Labels section for more details)](../../address-tags-and-labels/labels/). |
| label\_type       | [label](../../address-tags-and-labels/labels/) | The label type associated with the `user_address`column [(see Labels section for more details](../../address-tags-and-labels/labels/)).    |
| price             | number                                         | The average price of the token that day.                                                                                                   |
| symbol            | string                                         | Token symbol.                                                                                                                              |
| user\_address     | address                                        | The address the balance is for.                                                                                                            |
