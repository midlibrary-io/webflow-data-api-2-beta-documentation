# Publish Collection Item(s)

```
POST https://api.webflow.com/beta/collections/:collection_id/items/publish
```

Publish an item or multiple items.
**Required Scope:** `cms:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `publishedItemIds` | list of strings | No | N/A |
| `errors` | list of strings | No | N/A |




## Errors

* **400:** Items Publish Item Request Bad Request Error
* **401:** Items Publish Item Request Unauthorized Error
* **404:** Items Publish Item Request Not Found Error
* **429:** Items Publish Item Request Too Many Requests Error
* **500:** Items Publish Item Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/items/publish \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "itemIds": [
    "643fd856d66b6528195ee2ca",
    "643fd856d66b6528195ee2cb",
    "643fd856d66b6528195ee2cc"
  ]
}'
```

### Example Response (202 PrimaryLocale)

```json
{
  "publishedItemIds": [
    "643fd856d66b6528195ee2ca",
    "643fd856d66b6528195ee2cb"
  ],
  "errors": [
    "Staging item ID 643fd856d66b6528195ee2cf not found."
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/staged-items/publish-item](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/staged-items/publish-item)*