# Get Custom Code

```
GET https://api.webflow.com/beta/sites/:site_id/custom_code
```

Get all scripts applied to a site by the App.
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
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/custom_code \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "scripts": [
    {
      "id": "cms_slider",
      "location": "header",
      "version": "1.0.0",
      "attributes": {
        "my-attribute": "some-value"
      }
    },
    {
      "id": "alert",
      "location": "header",
      "version": "0.0.1",
      "attributes": {
        "key": "value"
      }
    }
  ],
  "lastUpdated": "2022-10-26T00:28:54.191Z",
  "createdOn": "2022-10-26T00:28:54.191Z"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code-sites/get-custom-code](https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code-sites/get-custom-code)*