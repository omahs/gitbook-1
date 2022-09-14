# NFT Metadata

{% hint style="warning" %}
These legacy Ethereum tables are deprecated. See [Ethereum Core](../../ethereum-core-tables/) for up-to-date Ethereum models.
{% endhint %}

NFT Metadata exists within the `ethereum` schema, as `ethereum.nft_metadata`

| Field                  | Type      | Description                                                                                                                                                                                      |
| ---------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `blockchain`           | string    | ethereum                                                                                                                                                                                         |
| `project_name`         | string    | the platform where the nft was minted. Note that nft's minted through opensea and rarible are specially labeled as opensea\_nfts and rarible\_nfts to distinguish them from the marketplaces     |
| `contract_address`     | address   | address of the NFT contract                                                                                                                                                                      |
| `contract_name`        | string    | name of the NFT contract as recorded IN the contract (sometimes the same as platform, sometimes not)                                                                                             |
| `token_id`             | number    | the token\_id of the NFT that the metdata is for                                                                                                                                                 |
| `created_at_block_id`  | number    | block where the NFT was minted                                                                                                                                                                   |
| `created_at_timestamp` | timestamp | timestamp of the block where the NFT was minted                                                                                                                                                  |
| `creator_address`      | address   | art NFT's only - address of the creator                                                                                                                                                          |
| `creator_name`         | string    | art NFT's only - name or username of the creator                                                                                                                                                 |
| `commission_rate`      | number    | art NFT's only - artist's commission rate, where available                                                                                                                                       |
| `token_name`           | string    | name of the token - especially relevant for art nfts. note that we're not recording the names of hashmasks as they can change at any time                                                        |
| `image_url`            | url       | the image of the NFT                                                                                                                                                                             |
| `token_metadata`       | json      | <p>json of metadata, note that when querying a piece of this json, you can do so like this: <code>token_metadata:[name of thing you want]</code>, <br>e.g. <code>token_metadata:color</code></p> |
| `token_metadata_url`   | url       | link to the metadata json                                                                                                                                                                        |
