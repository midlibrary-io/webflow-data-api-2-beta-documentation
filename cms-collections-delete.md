# Delete Collection

```
DELETE https://api.webflow.com/beta/collections/:collection_id
```

Delete a collection using its ID.
**Required Scope:** `cms:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |




## Errors

* **400:** Collections Delete Request Bad Request Error
* **401:** Collections Delete Request Unauthorized Error
* **404:** Collections Delete Request Not Found Error
* **429:** Collections Delete Request Too Many Requests Error
* **500:** Collections Delete Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745 \
     -H "Authorization: Bearer <token>"
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collections/delete](https://developers.webflow.com/v2.0.0-beta/reference/cms/collections/delete)*