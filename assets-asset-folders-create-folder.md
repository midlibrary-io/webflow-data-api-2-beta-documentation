# Create Asset Folder

```
POST https://api.webflow.com/beta/sites/:site_id/asset_folders
```

Create an Asset Folder within a given site
**Required Scope:** `assets:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | Unique identifier for the Asset Folder |
| `displayName` | string | No | User visible name for the Asset Folder |
| `parentFolder` | string | No | Pointer to parent Asset Folder (or null if root) |
| `assets` | list of strings | No | Array of Asset instances in the folder |
| `siteId` | string | No | The unique ID of the site the Asset Folder belongs to |
| `createdOn` | datetime | No | Date that the Asset Folder was created on |
| `lastUpdated` | datetime | No | Date that the Asset Folder was last updated on |




## Errors

* **400:** Assets Create Folder Request Bad Request Error
* **401:** Assets Create Folder Request Unauthorized Error
* **404:** Assets Create Folder Request Not Found Error
* **429:** Assets Create Folder Request Too Many Requests Error
* **500:** Assets Create Folder Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/asset_folders \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "displayName": "my asset folder"
}'
```

### Example Response (200 Successful)

```json
{
  "id": "6390c49774a71f0e3c1a08ee",
  "displayName": "emoji icons",
  "parentFolder": "6390c49774a71f99f21a08eb",
  "assets": [
    "63e5889e7fe4eafa7384cea4",
    "659595234426a9fcbad57043"
  ],
  "siteId": "6390c49674a71f84b51a08d8",
  "createdOn": "2018-10-14T21:55:49Z",
  "lastUpdated": "2022-12-07T16:51:37Z"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/assets/asset-folders/create-folder](https://developers.webflow.com/v2.0.0-beta/reference/assets/asset-folders/create-folder)*