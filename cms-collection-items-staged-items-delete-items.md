# Delete Collection Item(s)

```
DELETE https://api.webflow.com/beta/collections/:collection_id/items
```

Delete Items from a Collection.
Note:If thecmsLocaleIdparameter is undefined or empty and the items are localized, items will be deleted only in the primary locale.
**Required Scope:** `CMS:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |




## Errors

* **400:** Items Delete Items Request Bad Request Error
* **401:** Items Delete Items Request Unauthorized Error
* **404:** Items Delete Items Request Not Found Error
* **429:** Items Delete Items Request Too Many Requests Error
* **500:** Items Delete Items Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/items \
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
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/staged-items/delete-items](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/staged-items/delete-items)*