# List Asset Folders

```
GET https://api.webflow.com/beta/sites/:site_id/asset_folders
```

List Asset Folders within a given site
**Required Scope:** `assets:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `assetFolders` | list of objects | No | A list of Asset folders |
| `assetFolders.id` | string | No | Unique identifier for the Asset Folder |
| `assetFolders.displayName` | string | No | User visible name for the Asset Folder |
| `assetFolders.parentFolder` | string | No | Pointer to parent Asset Folder (or null if root) |
| `assetFolders.assets` | list of strings | No | Array of Asset instances in the folder |
| `assetFolders.siteId` | string | No | The unique ID of the site the Asset Folder belongs to |
| `assetFolders.createdOn` | datetime | No | Date that the Asset Folder was created on |
| `assetFolders.lastUpdated` | datetime | No | Date that the Asset Folder was last updated on |
| `pagination` | object | No | Pagination object |
| `pagination.limit` | double | No | The limit used for pagination |
| `pagination.offset` | double | No | The offset used for pagination |
| `pagination.total` | double | No | The total number of records |




## Errors

* **400:** Assets List Folders Request Bad Request Error
* **401:** Assets List Folders Request Unauthorized Error
* **404:** Assets List Folders Request Not Found Error
* **429:** Assets List Folders Request Too Many Requests Error
* **500:** Assets List Folders Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/asset_folders \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "assetFolders": [
    {
      "id": "6390c49774a71f0e3c1a08ee",
      "displayName": "emoji icons",
      "assets": [
        "63e5889e7fe4eafa7384cea4",
        "659595234426a9fcbad57043"
      ],
      "siteId": "6390c49674a71f84b51a08d8",
      "createdOn": "2018-10-14T21:55:49Z",
      "lastUpdated": "2022-12-07T16:51:37Z"
    }
  ],
  "pagination": {
    "limit": 1,
    "offset": 0,
    "total": 1
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/assets/asset-folders/list-folders](https://developers.webflow.com/v2.0.0-beta/reference/assets/asset-folders/list-folders)*