# List Custom Code Blocks

```
GET https://api.webflow.com/beta/sites/:site_id/custom_code/blocks
```

Get a list of scripts that have been applied to a site and/or individual pages.
**Required Scope:** `custom_code:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `offset` | double | No | Offset used for pagination if the results have more than limit records |
| `limit` | double | No | Maximum number of records to be returned (max limit: 100) |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `blocks` | list of objects | No | N/A |
| `blocks.siteId` | string | No | The Site ID where the custom code was applied |
| `blocks.pageId` | string | No | The Page ID (if applied at Page-level) |
| `blocks.type` | enum | No | Whether the Custom Code script is applied at the Site-level or Page-level (Values: page, site) |
| `blocks.scripts` | list of objects | No | A list of scripts applied to a Site or a Page |
| `blocks.scripts.id` | string | No | ID of the registered custom code script |
| `blocks.scripts.location` | enum | No | Location of the script, either in the header or footer of the published site (Values: header, footer) |
| `blocks.scripts.version` | string | No | Semantic Version String for the registered scripte.g. 0.0.1 |
| `blocks.scripts.attributes` | map from strings to any | No | Developer-specified key/value pairs to be applied as attributes to the script |
| `blocks.createdOn` | datetime | No | The date the Block was created |
| `blocks.lastUpdated` | datetime | No | The date the Block was most recently updated |
| `pagination` | object | No | Pagination object |
| `pagination.limit` | double | No | The limit used for pagination |
| `pagination.offset` | double | No | The offset used for pagination |
| `pagination.total` | double | No | The total number of records |




## Errors

* **400:** Scripts List Custom Code Blocks Request Bad Request Error
* **401:** Scripts List Custom Code Blocks Request Unauthorized Error
* **404:** Scripts List Custom Code Blocks Request Not Found Error
* **429:** Scripts List Custom Code Blocks Request Too Many Requests Error
* **500:** Scripts List Custom Code Blocks Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/custom_code/blocks \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "blocks": [
    {
      "siteId": "6258612d1ee792848f805dcf",
      "type": "site",
      "scripts": [
        {
          "id": "chartjs",
          "location": "header",
          "version": "4.4.2",
          "attributes": {
            "key": "value"
          }
        }
      ],
      "createdOn": "2024-04-03T16:49:15Z",
      "lastUpdated": "2024-04-03T16:49:15Z"
    },
    {
      "siteId": "6390c49674a71f84b51a08d8",
      "pageId": "6419db964a9c43f6a3af6348",
      "type": "page",
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
      "createdOn": "2022-10-26T00:28:54Z",
      "lastUpdated": "2022-10-26T00:28:54Z"
    }
  ],
  "pagination": {
    "limit": 10,
    "offset": 0,
    "total": 1
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code-sites/list-custom-code-blocks](https://developers.webflow.com/v2.0.0-beta/reference/custom-code/custom-code-sites/list-custom-code-blocks)*