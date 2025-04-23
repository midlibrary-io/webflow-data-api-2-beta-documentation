# Delete Custom Code

```
DELETE https://api.webflow.com/beta/pages/:page_id/custom_code
```

Delete a custom code block that the App created on a page.
**Required Scope:** `custom_code:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `page_id` | string | Yes | Unique identifier for a Page |




## Errors

* **400:** Scripts Delete Custom Code Request Bad Request Error
* **401:** Scripts Delete Custom Code Request Unauthorized Error
* **404:** Scripts Delete Custom Code Request Not Found Error
* **429:** Scripts Delete Custom Code Request Too Many Requests Error
* **500:** Scripts Delete Custom Code Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/pages/63c720f9347c2139b248e552/custom_code \
     -H "Authorization: Bearer <token>"
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code-pages/delete-custom-code](https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code-pages/delete-custom-code)*