---
description: Lower-level Direct HTTP Access
---

# 🔗 RestAPI

Welcome to the RestAPI Docs for ShroomDK.&#x20;

{% hint style="info" %}
Don't see an SDK for your language of choice? Interact directly with the RestAPI endpoints below! If you're feeling adventurous feel free to build an SDK library -- we'd be happy to point the community to it.
{% endhint %}

There are two endpoints in the API.

1. Create a Query: used to queue up the execution of a query.
2. Get Query Results: used to retrieve results from a #1.

### Create a Query

The following endpoint will queue up the execution of a query. If results already exist the query will not be executed. The endpoint returns a `token` that can be plugged into the `Get Query Results` endpoint to retrieve your data.

{% swagger src="../.gitbook/assets/rest_api.yml" path="/queries" method="post" %}
[rest_api.yml](../.gitbook/assets/rest_api.yml)
{% endswagger %}

### Get Query Results

This endpoint takes as input a `token` from a `Create Query` response.

{% swagger src="../.gitbook/assets/rest_api.yml" path="/queries/{token}" method="get" %}
[rest_api.yml](../.gitbook/assets/rest_api.yml)
{% endswagger %}

### Example in Python:

The following example calls the two endpoints above to run a query and retrieve the results.

```python
import requests
import json
import time

API_KEY = "YOUR-API-KEY-HERE"

SQL_QUERY = """
    SELECT 
        nft_address, 
        mint_price_eth, 
        mint_price_usd 
    FROM ethereum.core.ez_nft_mints 
    LIMIT 2
"""

TTL_MINUTES = 15

# return up to 100,000 results per GET request on the query id
PAGE_SIZE = 100000

# return results of page 1
PAGE_NUMBER = 1

def create_query():
    r = requests.post(
        'https://node-api.flipsidecrypto.com/queries', 
        data=json.dumps({
            "sql": SQL_QUERY,
            "ttlMinutes": TTL_MINUTES
        }),
        headers={"Accept": "application/json", "Content-Type": "application/json", "x-api-key": API_KEY},
    )
    if r.status_code != 200:
        raise Exception("Error creating query, got response: " + r.text + "with status code: " + str(r.status_code))
    
    return json.loads(r.text)    


def get_query_results(token):
    r = requests.get(
        'https://node-api.flipsidecrypto.com/queries/{token}?pageNumber={page_number}&pageSize={page_size}'.format(
          token=token,
          page_number=PAGE_NUMBER,
          page_size=PAGE_SIZE
        ),
        headers={"Accept": "application/json", "Content-Type": "application/json", "x-api-key": API_KEY}
    )
    if r.status_code != 200:
        raise Exception("Error getting query results, got response: " + r.text + "with status code: " + str(r.status_code))
    
    data = json.loads(r.text)
    if data['status'] == 'running':
        time.sleep(10)
        return get_query_results(token)

    return data


def run():
    query = create_query()
    token = query.get('token')
    data = get_query_results(token)

    print(data['columnLabels'])
    for row in data['results']:
        print(row)


if __name__ == '__main__':
    run()
```

### Pagination

For large data sets the "Get Query Results" endpoint supports `pageSize` and `pageNumber` parameters that can be used to retrieve subsets of query results.

By default, the endpoint will return up to 100k records.

More details on query pagination here:

{% content-ref url="query-pagination/" %}
[query-pagination](query-pagination/)
{% endcontent-ref %}
