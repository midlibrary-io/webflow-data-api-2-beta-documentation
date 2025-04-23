# Remove Webhook

```
DELETE https://api.webflow.com/beta/webhooks/:webhook_id
```

Remove a Webhook
**Required Scope:** `sites:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `webhook_id` | string | Yes | Unique identifier for a Webhook |




## Errors

* **400:** Webhooks Delete Request Bad Request Error
* **401:** Webhooks Delete Request Unauthorized Error
* **404:** Webhooks Delete Request Not Found Error
* **429:** Webhooks Delete Request Too Many Requests Error
* **500:** Webhooks Delete Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X DELETE https://api.webflow.com/beta/webhooks/580e64008c9a982ac9b8b754 \
     -H "Authorization: Bearer <token>"
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/webhooks/webhooks/delete](https://developers.webflow.com/v2.0.0-beta/reference/webhooks/webhooks/delete)*