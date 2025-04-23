# Create Localized Collection Item(s)

```
POST https://api.webflow.com/beta/collections/:collection_id/items/bulk
```

Create an item or multiple items in a CMS Collection across multiple corresponding locales.
Notes:
**Required Scope:** `CMS:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | Unique identifier for the Item |
| `cmsLocaleIds` | list of strings | No | Array of identifiers for the locales where the item will be created |
| `lastPublished` | string | No | The date the item was last published |
| `lastUpdated` | string | No | The date the item was last updated |
| `createdOn` | string | No | The date the item was created |
| `isArchived` | boolean | No | Boolean determining if the Item is set to archived |
| `isDraft` | boolean | No | Boolean determining if the Item is set to draft |
| `fieldData` | object | No | N/A |
| `fieldData.name` | string | No | Name of the Item |
| `fieldData.slug` | string | No | URL structure of the Item in your site. Note: Updates to an item slug will break all links referencing the old slug. |




## Errors

* **400:** Items Create Items Request Bad Request Error
* **401:** Items Create Items Request Unauthorized Error
* **404:** Items Create Items Request Not Found Error
* **429:** Items Create Items Request Too Many Requests Error
* **500:** Items Create Items Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/items/bulk \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "cmsLocaleIds": [
    "66f6e966c9e1dc700a857ca3",
    "66f6e966c9e1dc700a857ca4",
    "66f6e966c9e1dc700a857ca5"
  ],
  "isArchived": false,
  "isDraft": true,
  "fieldData": {
    "name": "Don’t Panic",
    "slug": "dont-panic"
  }
}'
```

### Example Response (202 Create a single item across multiple locales)

```json
{
  "id": "580e64008c9a982ac9b8b754",
  "cmsLocaleIds": [
    "653ad57de882f528b32e810e",
    "6514390aea353fc691d69827",
    "65143930ea353fc691d69cd8"
  ],
  "lastPublished": "2023-03-17T18:47:35.560Z",
  "lastUpdated": "2023-03-17T18:47:35.560Z",
  "createdOn": "2023-03-17T18:47:35.560Z",
  "isArchived": true,
  "isDraft": true,
  "fieldData": {
    "name": "My new item",
    "slug": "my-new-item",
    "date": "2022-11-18T00:00:00.000Z",
    "featured": false,
    "color": "#db4b68"
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/staged-items/create-items](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/staged-items/create-items)*