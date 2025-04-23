# Delete a well-known file

```
DELETE https://api.webflow.com/beta/sites/:site_id/well_known
```

Delete existing well-known files from a site.
**Required Scope:** `site_config:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Errors

* **400:** Well Known Delete Request Bad Request Error
* **401:** Well Known Delete Request Unauthorized Error
* **404:** Well Known Delete Request Not Found Error
* **429:** Well Known Delete Request Too Many Requests Error
* **500:** Well Known Delete Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/well_known \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-config/well-known-files/delete](https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-config/well-known-files/delete)*