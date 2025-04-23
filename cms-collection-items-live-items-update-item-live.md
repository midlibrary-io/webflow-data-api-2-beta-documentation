# Update Single Live Collection Item

```
PATCH https://api.webflow.com/beta/collections/:collection_id/items/:item_id/live
```

Update a selected live Item in a Collection. The updates for this Item will be published to the live site.
**Required Scope:** `CMS:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |
| `item_id` | string | Yes | Unique identifier for an Item |




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

* **400:** Items Update Item Live Request Bad Request Error
* **401:** Items Update Item Live Request Unauthorized Error
* **404:** Items Update Item Live Request Not Found Error
* **409:** Items Update Item Live Request Conflict Error
* **429:** Items Update Item Live Request Too Many Requests Error
* **500:** Items Update Item Live Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X PATCH https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/items/580e64008c9a982ac9b8b754/live \
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

### Example Response (200 Updated)

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
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/live-items/update-item-live](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/live-items/update-item-live)*