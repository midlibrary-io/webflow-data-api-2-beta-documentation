# Update Collection Item(s)

```
PATCH https://api.webflow.com/beta/collections/:collection_id/items
```

Update a single item or multiple items (up to 100) in a Collection.
Note:If thecmsLocaleIdparameter is undefined or empty and the items are localized, items will be updated only in the primary locale.
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
| `fieldData` | object | No | N/A |
| `fieldData.name` | string | No | Name of the Item |
| `fieldData.slug` | string | No | URL structure of the Item in your site. Note: Updates to an item slug will break all links referencing the old slug. |
| `cmsLocaleId` | string | No | Identifier for the locale of the CMS item |
| `isArchived` | boolean | No | Boolean determining if the Item is set to archived |
| `isDraft` | boolean | No | Boolean determining if the Item is set to draft |




## Errors

* **400:** Items Update Items Request Bad Request Error
* **401:** Items Update Items Request Unauthorized Error
* **404:** Items Update Items Request Not Found Error
* **429:** Items Update Items Request Too Many Requests Error
* **500:** Items Update Items Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X PATCH https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/items \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "items": [
    {
      "id": "66f6ed9576ddacf3149d5ea6",
      "cmsLocaleId": "66f6e966c9e1dc700a857ca5",
      "fieldData": {
        "name": "Ne Paniquez Pas",
        "slug": "ne-paniquez-pas",
        "featured": false
      }
    },
    {
      "id": "66f6ed9576ddacf3149d5ea6",
      "cmsLocaleId": "66f6e966c9e1dc700a857ca4",
      "fieldData": {
        "name": "No Entrar en Pánico",
        "slug": "no-entrar-en-panico",
        "featured": false
      }
    },
    {
      "id": "66f6ed9576ddacf3149d5eaa",
      "cmsLocaleId": "66f6e966c9e1dc700a857ca5",
      "fieldData": {
        "name": "Au Revoir et Merci pour Tous les Poissons",
        "slug": "au-revoir-et-merci",
        "featured": false
      }
    },
    {
      "id": "66f6ed9576ddacf3149d5eaa",
      "cmsLocaleId": "66f6e966c9e1dc700a857ca4",
      "fieldData": {
        "name": "Hasta Luego y Gracias por Todo el Pescado",
        "slug": "hasta-luego-y-gracias",
        "featured": false
      }
    }
  ]
}'
```

### Example Response (200 LocalizedItems)

```json
{
  "id": "580e64008c9a982ac9b8b754",
  "lastPublished": "2023-03-17T18:47:35.560Z",
  "lastUpdated": "2023-03-17T18:47:35.560Z",
  "createdOn": "2023-03-17T18:47:35.560Z",
  "fieldData": {
    "name": "My new item",
    "slug": "my-new-item",
    "date": "2022-11-18T00:00:00.000Z",
    "featured": false,
    "color": "#db4b68"
  },
  "cmsLocaleId": "653ad57de882f528b32e810e",
  "isArchived": true,
  "isDraft": true
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/staged-items/update-items](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/staged-items/update-items)*