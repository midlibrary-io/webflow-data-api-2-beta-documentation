# Delete Collection Field

```
DELETE https://api.webflow.com/beta/collections/:collection_id/fields/:field_id
```

Delete a custom field in a collection. This endpoint does not currently support bulk deletion.
**Required Scope:** `cms:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |
| `field_id` | string | Yes | Unique identifier for a Field in a collection |




## Errors

* **400:** Fields Delete Request Bad Request Error
* **401:** Fields Delete Request Unauthorized Error
* **404:** Fields Delete Request Not Found Error
* **429:** Fields Delete Request Too Many Requests Error
* **500:** Fields Delete Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/fields/580e63fc8c9a982ac9b8b745 \
     -H "Authorization: Bearer <token>"
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-fields/delete](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-fields/delete)*