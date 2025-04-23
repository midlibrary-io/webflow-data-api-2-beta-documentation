# Delete Live Collection Item(s)

```
DELETE https://api.webflow.com/beta/collections/:collection_id/items/live
```

Remove an item or multiple items (up to 100 items) from the live site.
Using this endpoint to delete published item(s) will unpublish the item(s) from the live site and set the item(s)isDraftproperty totrue.
**Required Scope:** `CMS:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |




## Errors

* **400:** Items Delete Items Live Request Bad Request Error
* **401:** Items Delete Items Live Request Unauthorized Error
* **404:** Items Delete Items Live Request Not Found Error
* **429:** Items Delete Items Live Request Too Many Requests Error
* **500:** Items Delete Items Live Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/items/live \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "items": [
    {
      "id": "580e64008c9a982ac9b8b754"
    }
  ]
}'
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/live-items/delete-items-live](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/live-items/delete-items-live)*