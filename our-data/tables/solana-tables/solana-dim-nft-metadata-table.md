# Solana Dim NFT Metadata Table

### Table Schema

solana.dim\_nft\_metadata

| Field                  | Type      | Description                                                                                                  |
| ---------------------- | --------- | ------------------------------------------------------------------------------------------------------------ |
| blockchain             | string    | In this table, always Solana. Used to join to cross-chain tables.                                            |
| contract\_address      | string    | Address unique to an NFT series.                                                                             |
| contract\_name         | string    | Name of the contract that identifies an NFT series. Example - tcgdragons.                                    |
| created\_at\_timestamp | timestamp | Timestamp in UTC that the NFT was minted at.                                                                 |
| mint                   | string    | Unique address representing a specific token.                                                                |
| creator\_address       | string    | Address provided by the creator of the project where mint payments and secondary market royalties are sent.  |
| creator\_name          | string    | Name of the project creator - this can be an individual or a company name.                                   |
| image\_url             | string    | URL that links to the image on the ipfs service.                                                             |
| project\_name          | string    | Name of the project the NFT token belongs to.                                                                |
| token\_id              | integer   | Numeric value that identifies the NFT within it's series.                                                    |
| token\_metadata        | array     | A block of json that describes the traits of an NFT.                                                         |
| token\_metadata\_uri   | string    | URL that links to the token metadata on the ipfs service.                                                    |
| token\_name            | string    | Name of the NFT token - this is unique to token. Example SMB #284.                                           |

