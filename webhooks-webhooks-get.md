# Get Webhook

```
GET https://api.webflow.com/beta/webhooks/:webhook_id
```

Get a specific Webhook instance
**Required Scope:** `sites:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `webhook_id` | string | Yes | Unique identifier for a Webhook |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | Unique identifier for the Webhook registration |
| `triggerType` | enum | No | The type of event that triggered the request. See the the documentation for details onsupported events. (Values: form_submission, site_publish, page_created, page_metadata_updated, page_deleted, ecomm_new_order, ecomm_order_changed, ecomm_inventory_changed, user_account_added, user_account_updated, user_account_deleted, collection_item_created, collection_item_changed, collection_item_deleted, collection_item_unpublished, comment_created) |
| `url` | string | No | URL to send the Webhook payload to |
| `workspaceId` | string | No | Unique identifier for the Workspace the Webhook is registered in |
| `siteId` | string | No | Unique identifier for the Site the Webhook is registered in |
| `filter` | object | No | Only supported for theform_submissiontrigger type. Filter for the form you want Webhooks to be sent for. |
| `filter.name` | string | No | The name of the form you’d like to recieve notifications for. |
| `lastTriggered` | datetime | No | Date the Webhook instance was last triggered |
| `createdOn` | datetime | No | Date the Webhook registration was created |




## Errors

* **400:** Webhooks Get Request Bad Request Error
* **401:** Webhooks Get Request Unauthorized Error
* **404:** Webhooks Get Request Not Found Error
* **429:** Webhooks Get Request Too Many Requests Error
* **500:** Webhooks Get Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/webhooks/580e64008c9a982ac9b8b754 \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "id": "582266e0cd48de0f0e3c6d8b",
  "triggerType": "form_submission",
  "url": "https://webhook.site/7f7f7f7f-7f7f-7f7f-7f7f-7f7f7f7f7f7f",
  "workspaceId": "4f4e46fd476ea8c507000001",
  "siteId": "562ac0395358780a1f5e6fbd",
  "lastTriggered": "2023-02-08T23:59:28Z",
  "createdOn": "2022-11-08T23:59:28Z"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/webhooks/webhooks/get](https://developers.webflow.com/v2.0.0-beta/reference/webhooks/webhooks/get)*