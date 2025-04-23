# Update Page Content

```
POST https://api.webflow.com/beta/pages/:page_id/dom
```

This endpoint updates content on a static page insecondary locales. It supports updating up to 1000 nodes in a single request.
Before making updates:
**Required Scope:** `pages:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `page_id` | string | Yes | Unique identifier for a Page |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `localeId` | string | Yes | The locale identifier. |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `errors` | list of strings | No | A list of error messages, if any. |




## Errors

* **400:** Update Static Content Request Bad Request Error
* **401:** Update Static Content Request Unauthorized Error
* **403:** Update Static Content Request Forbidden Error
* **404:** Update Static Content Request Not Found Error
* **429:** Update Static Content Request Too Many Requests Error
* **500:** Update Static Content Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST "https://api.webflow.com/beta/pages/63c720f9347c2139b248e552/dom?localeId=localeId" \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "nodes": [
    {
      "nodeId": "a245c12d-995b-55ee-5ec7-aa36a6cad623",
      "text": "<h1>The Hitchhiker\'s Guide to the Galaxy</h1>"
    },
    {
      "nodeId": "a245c12d-995b-55ee-5ec7-aa36a6cad627",
      "text": "<div><h3>Don\'t Panic!</h3><p>Always know where your towel is.</p></div>"
    },
    {
      "nodeId": "a245c12d-995b-55ee-5ec7-aa36a6cad635",
      "choices": [
        {
          "value": "choice-1",
          "text": "First choice"
        },
        {
          "value": "choice-2",
          "text": "Second choice"
        }
      ]
    },
    {
      "nodeId": "a245c12d-995b-55ee-5ec7-aa36a6cad642",
      "placeholder": "Enter something here..."
    },
    {
      "nodeId": "a245c12d-995b-55ee-5ec7-aa36a6cad671",
      "value": "Submit",
      "waitingText": "Submitting..."
    },
    {
      "nodeId": "a245c12d-995b-55ee-5ec7-aa36a6cad629",
      "propertyOverrides": [
        {
          "propertyId": "7dd14c08-2e96-8d3d-2b19-b5c03642a0f0",
          "text": "<div><h1>Time is an <em>illusion</em></h1></div>"
        },
        {
          "propertyId": "7dd14c08-2e96-8d3d-2b19-b5c03642a0f1",
          "text": "Life, the Universe and Everything"
        }
      ]
    }
  ]
}'
```

### Example Response (200 Successful)

```json
{
  "errors": [
    "errors"
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/pages/update-static-content](https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/pages/update-static-content)*