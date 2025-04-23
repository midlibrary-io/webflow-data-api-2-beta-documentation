# Set a well-known file

```
PUT https://api.webflow.com/beta/sites/:site_id/well_known
```

Upload a supported well-known file to a site.
The current restrictions on well-known files are as follows:
**Required Scope:** `site_config:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Errors

* **400:** Well Known Put Request Bad Request Error
* **401:** Well Known Put Request Unauthorized Error
* **404:** Well Known Put Request Not Found Error
* **429:** Well Known Put Request Too Many Requests Error
* **500:** Well Known Put Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X PUT https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/well_known \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "fileName": "fileName",
  "fileData": "fileData"
}'
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-config/well-known-files/put](https://developers.webflow.com/v2.0.0-beta/reference/enterprise/site-config/well-known-files/put)*