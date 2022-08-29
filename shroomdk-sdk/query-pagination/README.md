---
description: Access subsets of your query results with pagination.
---

# 📄 Query Pagination

{% hint style="success" %}
Pagination is available by default in the REST API and starting at version 1.1.0 of the JS/TS SDK. Note this is a non-breaking release.&#x20;
{% endhint %}

At times you may find yourself needing to access a subset of your query results. Pagination allows you to do just that.

All query result sets return a maximum of 1,000,000 rows. The entire query result set is cached in accordance with the query’s TTL and subsets can be retrieved by specifying the page size and page number. All without rerunning the initial query and depleting your query run quota.

#### Defaults:

By default, all query runs will be set to the following if pagination is not specified.

| variable   | default value |
| ---------- | ------------- |
| pageSize   | 100k          |
| pageNumber | 1             |

#### Now let's dive into some SDK specific examples on how to handle pagination:

{% content-ref url="js-ts-pagination-example.md" %}
[js-ts-pagination-example.md](js-ts-pagination-example.md)
{% endcontent-ref %}

{% content-ref url="python-sdk-pagination-example.md" %}
[python-sdk-pagination-example.md](python-sdk-pagination-example.md)
{% endcontent-ref %}

{% content-ref url="rest-api-pagination-example.md" %}
[rest-api-pagination-example.md](rest-api-pagination-example.md)
{% endcontent-ref %}
