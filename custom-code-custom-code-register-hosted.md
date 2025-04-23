# Register Script - Hosted

```
POST https://api.webflow.com/beta/sites/:site_id/registered_scripts/hosted
```

Register a hosted script to a site.
**Required Scope:** `custom_code:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | Human readable id, derived from the user-specified display name |
| `canCopy` | boolean | No | Define whether the script can be copied on site duplication and transfer |
| `displayName` | string | No | User-facing name for the script. Must be between 1 and 50 alphanumeric characters |
| `hostedLocation` | string | No | URI for an externally hosted script location |
| `integrityHash` | string | No | Sub-Resource Integrity Hash. Only required for externally hosted scripts (passed via hostedLocation) |
| `createdOn` | string | No | Timestamp when the script version was created |
| `lastUpdated` | string | No | Timestamp when the script version was last updated |
| `version` | string | No | A Semantic Version (SemVer) string, denoting the version of the script |




## Errors

* **400:** Scripts Register Hosted Request Bad Request Error
* **401:** Scripts Register Hosted Request Unauthorized Error
* **404:** Scripts Register Hosted Request Not Found Error
* **429:** Scripts Register Hosted Request Too Many Requests Error
* **500:** Scripts Register Hosted Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/registered_scripts/hosted \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "hostedLocation": "https://cdn.jsdelivr.net/.../cmsslider.js",
  "integrityHash": "sha384-J+YlJ8v0gpaRoKH7SbFbEmxOZlAxLiwNjfSsBhDooGa5roXlPPpXbEevck4J7YZ+",
  "version": "1.0.0",
  "displayName": "CMS Slider",
  "canCopy": true
}'
```

### Example Response (201 Created)

```json
{
  "id": "cms_slider",
  "canCopy": true,
  "displayName": "CMS Slider",
  "hostedLocation": "https://cdn.jsdelivr.net/.../cmsslider.js",
  "integrityHash": "sha384-J+YlJ8v0gpaRoKH7SbFbEmxOZlAxLiwNjfSsBhDooGa5roXlPPpXbEevck4J7YZ+",
  "createdOn": "2022-10-26T00:28:54.191Z",
  "lastUpdated": "lastUpdated",
  "version": "1.0.0"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code/register-hosted](https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code/register-hosted)*