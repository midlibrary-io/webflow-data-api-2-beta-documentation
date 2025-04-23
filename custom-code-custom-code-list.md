# Get Registered Scripts

```
GET https://api.webflow.com/beta/sites/:site_id/registered_scripts
```

Get a list of scripts that have been registered to a site. A site can have a maximum of 800 registered scripts.
**Required Scope:** `custom_code:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `registeredScripts` | list of objects | No | N/A |
| `registeredScripts.id` | string | No | Human readable id, derived from the user-specified display name |
| `registeredScripts.canCopy` | boolean | No | Define whether the script can be copied on site duplication and transfer |
| `registeredScripts.displayName` | string | No | User-facing name for the script. Must be between 1 and 50 alphanumeric characters |
| `registeredScripts.hostedLocation` | string | No | URI for an externally hosted script location |
| `registeredScripts.integrityHash` | string | No | Sub-Resource Integrity Hash. Only required for externally hosted scripts (passed via hostedLocation) |
| `registeredScripts.createdOn` | string | No | Timestamp when the script version was created |
| `registeredScripts.lastUpdated` | string | No | Timestamp when the script version was last updated |
| `registeredScripts.version` | string | No | A Semantic Version (SemVer) string, denoting the version of the script |




## Errors

* **400:** Scripts List Request Bad Request Error
* **401:** Scripts List Request Unauthorized Error
* **404:** Scripts List Request Not Found Error
* **429:** Scripts List Request Too Many Requests Error
* **500:** Scripts List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/registered_scripts \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "registeredScripts": [
    {
      "id": "alert",
      "canCopy": false,
      "displayName": "Alert",
      "hostedLocation": "https://cdn.webflow.io/.../alert-0.0.1.js",
      "createdOn": "2022-10-26T00:28:54.191Z",
      "lastUpdated": "lastUpdated",
      "version": "0.0.1"
    },
    {
      "id": "alert",
      "canCopy": false,
      "displayName": "Alert",
      "hostedLocation": "https://cdn.webflow.io/.../alert-0.0.2.js",
      "createdOn": "2022-10-26T00:28:54.191Z",
      "lastUpdated": "lastUpdated",
      "version": "0.0.2"
    },
    {
      "id": "cms_slider",
      "canCopy": true,
      "displayName": "CMS Slider",
      "hostedLocation": "https://cdn.jsdelivr.net/.../cms_slider.js",
      "integrityHash": "sha384-J+YlJ8v0gpaRoKH7SbFbEmxOZlAxLiwNjfSsBhDooGa5roXlPPpXbEevck4J7YZ+",
      "createdOn": "2022-10-26T00:28:54.191Z",
      "lastUpdated": "lastUpdated",
      "version": "1.0.0"
    }
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code/list](https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code/list)*