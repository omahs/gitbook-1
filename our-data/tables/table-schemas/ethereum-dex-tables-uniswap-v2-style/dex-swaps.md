# DEX Swaps

{% hint style="warning" %}
These legacy Ethereum tables are deprecated. See [Ethereum Core](../../ethereum-core-tables.md) for up-to-date Ethereum models.
{% endhint %}

The liquidity swaps table (accessible through`ethereum.dex_swaps`) holds information on individual swap events, including the pool address, address of the swapped token, the address the swapped currency was sent to and the amount.

| Field             | Type      | Description                                                                                                                                                                                                                           |
| ----------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `block_timestamp` | timestamp | Time of the transaction that created the pool.                                                                                                                                                                                        |
| `pool_address`    | string    | Liquidity pools in Uniswap V2 style dexes are created with a `PairCreated` function. This is the hash of the original transaction that executed the function and created the pool.                                                    |
| `pool_name`       | address   | Name of the factory contract that created the pool. Many of these will be the factory contract used by Uniswap, but Sushiswap (and any others following the Uniswap V2 format) will also have their own factory contracts.            |
| `token_address`   | string    | Name of the pool in terms of the two tokens, i.e. 'UNI-WETH LP'. If no symbol information is present (for instance, for very small or new tokens) this will default to contract address to maintain an informative name               |
| `tx_id`           | address   | Address of the pool. Also equivalent to pool token, i.e. UNI-WETH LP liquidity providers are awarded UNI-WETH LP pool tokens with the same contract address                                                                           |
| `amount_in`       | address   | Token address of the first token held within the pool. The position token0/token1 is largely arbitrary -- derived from the original pool creation event, and used only in interpreting raw swap events (done by the associated table) |
| `amount_out`      | address   | Token address of the first token held within the pool. The position token0/token1 is largely arbitrary -- derived from the original pool creation event, and used only in interpreting raw swap events (done by the associated table) |
| `from_address`    | address   | Address that executed the swap (may be the router)                                                                                                                                                                                    |
| `to_address`      | address   | Address the swap amount was sent to                                                                                                                                                                                                   |
| `amount_usd`\*    | number    | Amount of the swap in USD                                                                                                                                                                                                             |
| `event_index`     | number    | Order of events in a transaction. One swap event will have two (for `IN`/`OUT`)                                                                                                                                                       |
| `direction`       | string    | `IN`/`OUT` depending on if the token is being sent to or from in the pool. Swap 10 A for 5 B, and A is `IN` and B is `OUT`                                                                                                            |

\*Calculated by taking the amount of tokens swapped times the average hourly (or daily, if hourly is not available) token price. This approach may cause high USD amounts for pools with low liquidity, trades with high slippage, tokens that go to $0, and tokens with massive supplies.

