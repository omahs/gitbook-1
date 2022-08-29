# ERC20 Balances Table

The `ethereum.erc20_balances` table contains daily roll-ups of balances for each address associated with an ERC-20 token. The table is updated throughout the day, to provide an intra-day view of balance readings as on-chain events occur.&#x20;

## Table Schema

`ethereum.erc20_balances`

| Field             | Type                               | Description                                                                                                                    |
| ----------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| address\_name     | [label](../../data-models/labels/) | [(see Labels section for details)](../../data-models/labels/)                                                                  |
| amount\_usd       | number                             | USD Value of the token balance                                                                                                 |
| balance           | number                             | Latest recorded balance for that given day and token.                                                                          |
| balance\_date     | string                             | UTC timestamp of the day the balance was recorded on.                                                                          |
| contract\_address | address                            | Token contract address.                                                                                                        |
| contract\_label   | [label](../../data-models/labels/) | The label associated with the `contract_address`[(see Labels section for more details)](../../data-models/labels/).            |
| label             | [label](../../data-models/labels/) | The label associated with the `user_address`column [(see Labels section for more details)](../../data-models/labels/).         |
| label\_subtype    | [label](../../data-models/labels/) | The label subtype associated with the `user_address`column [(see Labels section for more details)](../../data-models/labels/). |
| label\_type       | [label](../../data-models/labels/) | The label type associated with the `user_address`column [(see Labels section for more details](../../data-models/labels/)).    |
| price             | number                             | The average price of the token that day.                                                                                       |
| symbol            | string                             | Token symbol.                                                                                                                  |
| user\_address     | address                            | The address the balance is for.                                                                                                |
