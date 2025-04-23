# Register Script - Inline

```
POST https://api.webflow.com/beta/sites/:site_id/registered_scripts/inline
```

Register an inline script to a site. Inline scripts are limited to 2000 characters.
**Required Scope:** `custom_code:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Created_

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

* **400:** Scripts Register Inline Request Bad Request Error
* **401:** Scripts Register Inline Request Unauthorized Error
* **404:** Scripts Register Inline Request Not Found Error
* **429:** Scripts Register Inline Request Too Many Requests Error
* **500:** Scripts Register Inline Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/registered_scripts/inline \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "sourceCode": "alert(\'hello world\');",
  "version": "0.0.1",
  "displayName": "Alert"
}'
```

### Example Response (201 Created)

```json
{
  "id": "alert",
  "canCopy": false,
  "displayName": "Alert",
  "hostedLocation": "https://uploads-ssl.webflow.com/6258612d1ee792848f805dcf%2F64b6c769ff52ba6c3d904a91%2F660d6e15b3d1696f2d2b1447%2Falert-0.0.1.js",
  "createdOn": "2022-10-26T00:28:54.191Z",
  "lastUpdated": "lastUpdated",
  "version": "0.0.1"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code/register-inline](https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code/register-inline)*