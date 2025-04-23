# Get Asset Folder

```
GET https://api.webflow.com/beta/asset_folders/:asset_folder_id
```

Get details about a specific Asset Folder
**Required Scope:** `assets:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `asset_folder_id` | string | Yes | Unique identifier for an Asset Folder |




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

* **400:** Assets Get Folder Request Bad Request Error
* **401:** Assets Get Folder Request Unauthorized Error
* **404:** Assets Get Folder Request Not Found Error
* **429:** Assets Get Folder Request Too Many Requests Error
* **500:** Assets Get Folder Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/asset_folders/6390c49774a71f0e3c1a08ee \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

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
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/assets/asset-folders/get-folder](https://developers.webflow.com/v2.0.0-beta/reference/assets/asset-folders/get-folder)*