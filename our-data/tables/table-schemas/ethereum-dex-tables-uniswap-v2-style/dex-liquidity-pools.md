# DEX Liquidity Pools

{% hint style="warning" %}
These legacy Ethereum tables are deprecated. See [Ethereum Core](../../ethereum-core-tables/) for up-to-date Ethereum models.
{% endhint %}

The liquidity pools table (accessible through`ethereum.dex_liquidity_pools`) holds meta information on each pool created. (hint: Joining this table on `ethereum.erc20_balances` is one way to collect information on TVL, summing the balances of both tokens in the pool.)

As a further note worth highlighting the pool address is both the address that holds a balance of the two tokens _and_ the address of the pool token itself. So the address for UNI-WETH, will hold both UNI and WETH as a balance but the same address serves as the contract address for the pool token distributed to UNI-WETH liquidity providers.

| Field             | Type      | Description                                                                                                                                                                                                                           |
| ----------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `creation_time`   | timestamp | Time of the transaction that created the pool.                                                                                                                                                                                        |
| `creation_tx`     | string    | Liquidity pools in Uniswap V2 style dexes are created with a `PairCreated` function. This is the hash of the original transaction that executed the function and created the pool.                                                    |
| `factory_address` | address   | Name of the factory contract that created the pool. Many of these will be the factory contract used by Uniswap, but Sushiswap (and any others following the Uniswap V2 format) will also have their own factory contracts.            |
| `pool_name`       | string    | Name of the pool in terms of the two tokens, i.e. 'UNI-WETH LP'. If no symbol information is present (for instance, for very small or new tokens) this will default to contract address to maintain an informative name               |
| `pool_address`    | address   | Address of the pool. Also equivalent to pool token, i.e. UNI-WETH LP liquidity providers are awarded UNI-WETH LP pool tokens with the same contract address                                                                           |
| `token0`          | address   | Token address of the first token held within the pool. The position token0/token1 is largely arbitrary -- derived from the original pool creation event, and used only in interpreting raw swap events (done by the associated table) |
| `token1`          | address   | Token address of the first token held within the pool. The position token0/token1 is largely arbitrary -- derived from the original pool creation event, and used only in interpreting raw swap events (done by the associated table) |
