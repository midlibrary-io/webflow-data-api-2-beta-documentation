# Publish Site

```
POST https://api.webflow.com/beta/sites/:site_id/publish
```

Publishes a site to one or more more domains.
**Required Scope:** `sites:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request accepted_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `customDomains` | list of objects | No | Array of domains objects |
| `customDomains.id` | string | No | Unique identifier for the Domain |
| `customDomains.url` | string | No | The registered Domain name |
| `customDomains.lastPublished` | datetime | No | The date the custom domain was last published to |
| `publishToWebflowSubdomain` | boolean | No | Flag for publishing to webflow.io subdomain |




## Errors

* **400:** Sites Publish Request Bad Request Error
* **401:** Sites Publish Request Unauthorized Error
* **403:** Sites Publish Request Forbidden Error
* **404:** Sites Publish Request Not Found Error
* **429:** Sites Publish Request Too Many Requests Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/publish \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

### Example Response (202 Accepted)

```json
{
  "customDomains": [
    {
      "id": "589a331aa51e760df7ccb89d",
      "url": "test-api-domain.com",
      "lastPublished": "2022-12-07T16:51:37Z"
    }
  ],
  "publishToWebflowSubdomain": true
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/sites/publish](https://developers.webflow.com/v2.0.0-beta/reference/sites/publish)*