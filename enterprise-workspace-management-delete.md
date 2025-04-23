# Delete Site

```
DELETE https://api.webflow.com/beta/sites/:site_id
```

Delete a site.
**Required Scope:** `sites:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Errors

* **400:** Sites Delete Request Bad Request Error
* **401:** Sites Delete Request Unauthorized Error
* **403:** Sites Delete Request Forbidden Error
* **404:** Sites Delete Request Not Found Error
* **429:** Sites Delete Request Too Many Requests Error
* **500:** Sites Delete Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741 \
     -H "Authorization: Bearer <token>"
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/enterprise/workspace-management/delete](https://developers.webflow.com/v2.0.0-beta/reference/enterprise/workspace-management/delete)*