# Get Custom Code

```
GET https://api.webflow.com/beta/pages/:page_id/custom_code
```

Get all scripts applied to a page.
**Required Scope:** `custom_code:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `page_id` | string | Yes | Unique identifier for a Page |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `scripts` | list of objects | No | A list of scripts applied to a Site or a Page |
| `scripts.id` | string | No | ID of the registered custom code script |
| `scripts.location` | enum | No | Location of the script, either in the header or footer of the published site (Values: header, footer) |
| `scripts.version` | string | No | Semantic Version String for the registered scripte.g. 0.0.1 |
| `scripts.attributes` | map from strings to any | No | Developer-specified key/value pairs to be applied as attributes to the script |
| `lastUpdated` | string | No | Date when the Site’s scripts were last updated |
| `createdOn` | string | No | Date when the Site’s scripts were created |




## Errors

* **400:** Scripts Get Custom Code Request Bad Request Error
* **401:** Scripts Get Custom Code Request Unauthorized Error
* **404:** Scripts Get Custom Code Request Not Found Error
* **429:** Scripts Get Custom Code Request Too Many Requests Error
* **500:** Scripts Get Custom Code Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/pages/63c720f9347c2139b248e552/custom_code \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "scripts": [
    {
      "id": "id",
      "location": "header",
      "version": "version",
      "attributes": {
        "key": "value"
      }
    }
  ],
  "lastUpdated": "lastUpdated",
  "createdOn": "createdOn"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code-pages/get-custom-code](https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code-pages/get-custom-code)*