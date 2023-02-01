# Prices Pool Balances

This table can be used to price assets within the Algorand blockchain using on-chain liquidity pool. Price is calculated by end-of-hour pool balances on tinyman for Algo base pairs, then using the coinmarketcap/coingiecko ALGO price to calculate the price of the other asset

| Field              | Type      | Description                                                                                        |
| ------------------ | --------- | -------------------------------------------------------------------------------------------------- |
| BLOCK\_HOUR        | timestamp | The hour for which the price is valid                                                              |
| ASSET\_ID          | numeric   | ID associated with the asset                                                                       |
| ASSET\_NAME        | string    | Name of the asset                                                                                  |
| PRICE\_USD         | numeric   | The USD price of the asset at the end of the hour. ALGO price pulled from coinmarketcap/coingiecko |
| ALGO\_BALANCE      | numeric   | The balance of ALGO tokens in the pool at the end of the hour. NULL for ALGO                       |
| NON\_ALGO\_BALANCE | numeric   | The balance of other (non-ALGO) tokens in the pool at the end of the hour. NULL for ALGO           |
| POOL\_NAME         | string    | The name of the pool used for the price calculation. NULL for ALGO                                 |
| POOL\_ADDRESS      | string    | The address of the pool used for the price calculation. NULL for ALGO                              |
