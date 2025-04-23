# Create Live Collection Item(s)

```
POST https://api.webflow.com/beta/collections/:collection_id/items/live
```

Create item(s) in a collection that will be immediately published to the live site.
To create items across multiple locales,please use this endpoint.
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
| `lastPublished` | string | No | The date the item was last published |
| `lastUpdated` | string | No | The date the item was last updated |
| `createdOn` | string | No | The date the item was created |
| `isArchived` | boolean | No | Boolean determining if the Item is set to archived |
| `isDraft` | boolean | No | Boolean determining if the Item is set to draft |
| `fieldData` | object | No | N/A |
| `fieldData.name` | string | No | Name of the Item |
| `fieldData.slug` | string | No | URL structure of the Item in your site. Note: Updates to an item slug will break all links referencing the old slug. |
| `cmsLocaleId` | string | No | Identifier for the locale of the CMS item |




## Errors

* **400:** Items Create Item Live Request Bad Request Error
* **401:** Items Create Item Live Request Unauthorized Error
* **404:** Items Create Item Live Request Not Found Error
* **429:** Items Create Item Live Request Too Many Requests Error
* **500:** Items Create Item Live Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/items/live \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "isArchived": false,
  "isDraft": false,
  "fieldData": {
    "name": "Pan Galactic Gargle Blaster Recipe",
    "slug": "pan-galactic-gargle-blaster",
    "date": "2022-11-18T00:00:00.000Z",
    "featured": true,
    "color": "#db4b68"
  }
}'
```

### Example Response (202 SingleItem)

```json
{
  "id": "42b720ef280c7a7a3be8cabe",
  "lastPublished": "2022-11-29T16:22:43.159Z",
  "lastUpdated": "2022-11-17T17:19:43.282Z",
  "createdOn": "2022-11-17T17:11:57.148Z",
  "isArchived": false,
  "isDraft": false,
  "fieldData": {
    "name": "Pan Galactic Gargle Blaster Recipe",
    "slug": "pan-galactic-gargle-blaster",
    "color": "#db4b68",
    "date": "2022-11-18T00:00:00.000Z",
    "featured": true
  },
  "cmsLocaleId": "653ad57de882f528b32e810e"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/live-items/create-item-live](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/live-items/create-item-live)*