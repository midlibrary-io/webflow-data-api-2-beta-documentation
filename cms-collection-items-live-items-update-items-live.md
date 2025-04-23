# Update Live Collection Item(s)

```
PATCH https://api.webflow.com/beta/collections/:collection_id/items/live
```

Update a single published item or multiple published items (up to 100) in a Collection
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
| `items` | list of objects | No | List of Items within the collection |
| `items.id` | string | No | Unique identifier for the Item |
| `items.lastPublished` | string | No | The date the item was last published |
| `items.lastUpdated` | string | No | The date the item was last updated |
| `items.createdOn` | string | No | The date the item was created |
| `items.fieldData` | object | No | N/A |
| `items.fieldData.name` | string | No | Name of the Item |
| `items.fieldData.slug` | string | No | URL structure of the Item in your site. Note: Updates to an item slug will break all links referencing the old slug. |
| `items.cmsLocaleId` | string | No | Identifier for the locale of the CMS item |
| `items.isArchived` | boolean | No | Boolean determining if the Item is set to archived |
| `items.isDraft` | boolean | No | Boolean determining if the Item is set to draft |




## Errors

* **400:** Items Update Items Live Request Bad Request Error
* **401:** Items Update Items Live Request Unauthorized Error
* **404:** Items Update Items Live Request Not Found Error
* **409:** Items Update Items Live Request Conflict Error
* **429:** Items Update Items Live Request Too Many Requests Error
* **500:** Items Update Items Live Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X PATCH https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/items/live \
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
  "items": [
    {
      "id": "66f6ed9576ddacf3149d5ea6",
      "lastPublished": "2023-03-17T18:47:35.560Z",
      "lastUpdated": "2024-09-27T17:38:29.066Z",
      "createdOn": "2024-09-27T17:38:29.066Z",
      "fieldData": {
        "name": "Ne Paniquez Pas",
        "slug": "ne-paniquez-pas",
        "featured": false
      },
      "cmsLocaleId": "66f6e966c9e1dc700a857ca5",
      "isArchived": true,
      "isDraft": true
    },
    {
      "id": "66f6ed9576ddacf3149d5ea6",
      "lastPublished": "2023-03-17T18:47:35.560Z",
      "lastUpdated": "2024-09-27T17:38:29.066Z",
      "createdOn": "2024-09-27T17:38:29.066Z",
      "fieldData": {
        "name": "No Entrar en Pánico",
        "slug": "no-entrar-en-panico",
        "featured": false
      },
      "cmsLocaleId": "66f6e966c9e1dc700a857ca4",
      "isArchived": true,
      "isDraft": true
    },
    {
      "id": "66f6ed9576ddacf3149d5eaa",
      "lastPublished": "2023-03-17T18:47:35.560Z",
      "lastUpdated": "2024-09-27T17:38:29.066Z",
      "createdOn": "2024-09-27T17:38:29.066Z",
      "fieldData": {
        "name": "Au Revoir et Merci pour Tous les Poissons",
        "slug": "au-revoir-et-merci",
        "featured": false
      },
      "cmsLocaleId": "66f6e966c9e1dc700a857ca5",
      "isArchived": true,
      "isDraft": true
    },
    {
      "id": "66f6ed9576ddacf3149d5eaa",
      "lastPublished": "2023-03-17T18:47:35.560Z",
      "lastUpdated": "2024-09-27T17:38:29.066Z",
      "createdOn": "2024-09-27T17:38:29.066Z",
      "fieldData": {
        "name": "Hasta Luego y Gracias por Todo el Pescado",
        "slug": "hasta-luego-y-gracias",
        "featured": false
      },
      "cmsLocaleId": "66f6e966c9e1dc700a857ca4",
      "isArchived": true,
      "isDraft": true
    }
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/live-items/update-items-live](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/live-items/update-items-live)*