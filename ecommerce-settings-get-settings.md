# Get Ecommerce Settings

```
GET https://api.webflow.com/beta/sites/:site_id/ecommerce/settings
```

Retrieve ecommerce settings for a site.
**Required Scope:** `ecommerce:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `siteId` | string | No | The identifier of the Site |
| `createdOn` | datetime | No | Date that the Site was created on |
| `defaultCurrency` | string | No | The three-letter ISO currency code for the Site |




## Errors

* **400:** Ecommerce Get Settings Request Bad Request Error
* **401:** Ecommerce Get Settings Request Unauthorized Error
* **403:** Ecommerce Get Settings Request Forbidden Error
* **404:** Ecommerce Get Settings Request Not Found Error
* **409:** Ecommerce Get Settings Request Conflict Error
* **429:** Ecommerce Get Settings Request Too Many Requests Error
* **500:** Ecommerce Get Settings Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/ecommerce/settings \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "siteId": "5eb0b5583bf24e2d3a488969",
  "createdOn": "2018-10-04T15:21:02Z",
  "defaultCurrency": "USD"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/settings/get-settings](https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/settings/get-settings)*