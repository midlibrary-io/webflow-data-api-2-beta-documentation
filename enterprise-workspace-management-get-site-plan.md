# Get Site Plan

```
GET https://api.webflow.com/beta/sites/:site_id/plan
```

Get site plan details for the specified Site.
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
| `id` | enum | No | ID of the hosting plan. (Values: hosting-basic-v3, hosting-cms-v3, hosting-business-v3, hosting-ecommerce-standard-v2, hosting-ecommerce-plus-v2, hosting-ecommerce-advanced-v2, hosting-basic-v4, hosting-cms-v4, hosting-business-v4, hosting-ecommerce-standard-v3, hosting-ecommerce-plus-v3, hosting-ecommerce-advanced-v3) |
| `name` | enum | No | Name of the hosting plan. (Values: Basic Hosting, CMS Hosting, Business Hosting, ECommerce Standard Hosting, ECommerce Plus Hosting, ECommerce Advanced Hosting) |
| `pricingInfo` | string | No | URL for more information about Webflow hosting plan pricing. |




## Errors

* **400:** Plans Get Site Plan Request Bad Request Error
* **401:** Plans Get Site Plan Request Unauthorized Error
* **404:** Plans Get Site Plan Request Not Found Error
* **429:** Plans Get Site Plan Request Too Many Requests Error
* **500:** Plans Get Site Plan Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/plan \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "id": "hosting-business-v4",
  "name": "Business Hosting",
  "pricingInfo": "https://webflow.com/pricing"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/enterprise/workspace-management/get-site-plan](https://developers.webflow.com/v2.0.0-beta/reference/enterprise/workspace-management/get-site-plan)*