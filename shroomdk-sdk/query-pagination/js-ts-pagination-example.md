# JS/TS Pagination Example

In this query, we will request 200k records from the `ethereum.core.ez_nft_mints` table and return 100 records, starting at page #1.

```javascript
// Create a query object for the `query.run` function to execute
// with a page size of 100 rows, starting with page #1.
let query: Query = {
  sql: `
    SELECT
        nft_address,
        mint_price_eth,
        mint_price_usd
    FROM ethereum.core.ez_nft_mints
    LIMIT 200000
  `,
  ttlMinutes: 10,
  pageSize: 100,
  pageNumber: 1,
};

// Send the `Query` to Flipside's query engine and await the results for Page #1
const page1Results: QueryResultSet = await flipside.query.run(query);
```

Now if we'd like to access page #2, simply set `pageNumber` to 2 and re-run the query. This will return the next 100 rows (since we had set the `pageSize` to 100).&#x20;

```javascript
// update the pageNumber to the second page
query = {...query, pageNumber: 2}

const page2Results = await flipside.query.run(query)
```

{% hint style="info" %}
Updating the pageNumber does NOT re-execute the query and therefore does not deduct from your quota. Query results are cached (in accordance with the TTL) up to 1,000,000 records/rows.&#x20;
{% endhint %}
