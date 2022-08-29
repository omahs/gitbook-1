# 🔗 REST API Pagination Example

For example, let’s assume this is your query:

```sql
SELECT
  nft_address,
  mint_price_eth,
  mint_price_usd
FROM ethereum.core.ez_nft_mints
LIMIT 200000
```

To access the first 100 records you can issue a GET request with the following URL parameters to `/queries/<query-run-id>`

URL parameters:

`pageSize=100`

`pageNumber=1`

```
https://node-api.flipsidecrypto.com/queries/<query-run-id>?pageSize=100&pageNumber=1
```

To access the next page simply increment pageNumber to 2 and make the same HTTP GET request.

{% hint style="info" %}
Updating the pageNumber does NOT re-execute the query and therefore does not deduct from your quota. Query results are cached (in accordance with the TTL) up to 1,000,000 records/rows.&#x20;
{% endhint %}
