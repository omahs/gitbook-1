# 🐍 Python SDK Pagination Example

In this query, we will request 200k records from the `ethereum.core.ez_nft_mints` table and return 100 records, starting at page #1.

```python
from shroomdk import ShroomDK

sdk = ShroomDK("<YOUR_API_KEY>")

# Create a query object for the `query.run` function to execute
# with a page size of 100 rows, starting with page #1.
sql = """
  SELECT
    nft_address,
    mint_price_eth,
    mint_price_usd
  FROM ethereum.core.ez_nft_mints
  LIMIT 200000
"""

# Run the query on Flipside's Query Engine and await the results...
page_1_results = sdk.query(
  sql,
  page_size=100,
  page_number=1
)
```

Now if we'd like to access page #2, simply set the `page_number` argument to 2 and re-run the query. This will return the next 100 rows (since we had set the `page_size` to 100).&#x20;

```javascript
// update the page_number to the second page
page_2_results = sdk.query(query, page_size=100, page_number=2)
```

{% hint style="info" %}
Updating the `page_number` argument does NOT re-execute the query and therefore does not deduct from your quota. Query results are cached (in accordance with the TTL) up to 1,000,000 records/rows.&#x20;
{% endhint %}
