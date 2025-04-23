# Delete Custom Code

```
DELETE https://api.webflow.com/beta/sites/:site_id/custom_code
```

Remove scripts from a site applied by the App. This endpoint will not remove scripts from the site’s registered scripts.
**Required Scope:** `custom_code:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Errors

* **400:** Scripts Delete Custom Code Request Bad Request Error
* **401:** Scripts Delete Custom Code Request Unauthorized Error
* **404:** Scripts Delete Custom Code Request Not Found Error
* **429:** Scripts Delete Custom Code Request Too Many Requests Error
* **500:** Scripts Delete Custom Code Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/custom_code \
     -H "Authorization: Bearer <token>"
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code-sites/delete-custom-code](https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code-sites/delete-custom-code)*