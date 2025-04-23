# Delete Asset

```
DELETE https://api.webflow.com/beta/assets/:asset_id
```

Delete an Asset
**Required Scope:** `assets:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `asset_id` | string | Yes | Unique identifier for an Asset on a site |




## Errors

* **400:** Assets Delete Request Bad Request Error
* **401:** Assets Delete Request Unauthorized Error
* **404:** Assets Delete Request Not Found Error
* **429:** Assets Delete Request Too Many Requests Error
* **500:** Assets Delete Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/assets/580e63fc8c9a982ac9b8b745 \
     -H "Authorization: Bearer <token>"
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/assets/assets/delete](https://developers.webflow.com/v2.0.0-beta/reference/assets/assets/delete)*