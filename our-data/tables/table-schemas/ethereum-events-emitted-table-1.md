# Ethereum Contracts Table

Ethereum Contract metadata for ethereum contracts

Notable Features:

* Every contract has an associated name that corresponds 1:1 with the solidity contract code.
* Use for things like ERC20 Decimal Adjustments or Symbols (Metadata related to the contract)

## Table Schema

`ethereum.contracts`

| Field   | Type   | Description                    |
| ------- | ------ | ------------------------------ |
| Address | string | The ethereum contract address  |
| Meta    | json   | The ethereum contract metadata |
| Name    | string | The ethereum contract name     |
