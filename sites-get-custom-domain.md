# Get Custom Domains

```
GET https://api.webflow.com/beta/sites/:site_id/custom_domains
```

Get a list of all custom domains related to site.
**Required Scope:** `sites:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `customDomains` | list of objects | No | N/A |
| `customDomains.id` | string | No | Unique identifier for the Domain |
| `customDomains.url` | string | No | The registered Domain name |
| `customDomains.lastPublished` | datetime | No | The date the custom domain was last published to |




## Errors

* **401:** Sites Get Custom Domain Request Unauthorized Error
* **403:** Sites Get Custom Domain Request Forbidden Error
* **404:** Sites Get Custom Domain Request Not Found Error
* **429:** Sites Get Custom Domain Request Too Many Requests Error
* **500:** Sites Get Custom Domain Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/custom_domains \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "customDomains": [
    {
      "id": "589a331aa51e760df7ccb89d",
      "url": "hitchhikersguide.galaxy",
      "lastPublished": "2022-12-07T16:51:37Z"
    },
    {
      "id": "589a331aa51e760df7ccb89e",
      "url": "heartofgold.spaceship",
      "lastPublished": "2022-12-07T16:51:37Z"
    }
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/sites/get-custom-domain](https://developers.webflow.com/v2.0.0-beta/reference/sites/get-custom-domain)*