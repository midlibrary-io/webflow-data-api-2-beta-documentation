# List Live Collection Items

```
GET https://api.webflow.com/v2/collections/:collection_id/items/live
```

List all published items in a collection.
**Required Scope:** `CMS:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `cmsLocaleId` | string | No | Unique identifier for a CMS Locale. This UID is different from the Site locale identifier and is listed ascmsLocaleIdin the Sites response. To query multiple locales, input a comma separated string. |
| `offset` | double | No | Offset used for pagination if the results have more than limit records |
| `limit` | double | No | Maximum number of records to be returned (max limit: 100) |
| `name` | string | No | Filter by the exact name of the item(s) |
| `slug` | string | No | Filter by the exact slug of the item |
| `lastPublished` | object | No | Filter by the last published date of the item(s) |
| `lastPublished.lte` | datetime | No | Filter items last published before this date |
| `lastPublished.gte` | datetime | No | Filter items last published after this date |
| `lte` | datetime | No | Filter items last published before this date |
| `gte` | datetime | No | Filter items last published after this date |
| `sortBy` | enum | No | Sort results by the provided value (Values: lastPublished, name, slug) |
| `sortOrder` | enum | No | Sorts the results by asc or desc (Values: asc, desc) |




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
| `pagination` | object | No | N/A |
| `pagination.limit` | double | No | The limit specified in the request |
| `pagination.offset` | double | No | The offset specified for pagination |
| `pagination.total` | double | No | Total number of items in the collection |




## Errors

* **400:** Items List Items Live Request Bad Request Error
* **401:** Items List Items Live Request Unauthorized Error
* **404:** Items List Items Live Request Not Found Error
* **429:** Items List Items Live Request Too Many Requests Error
* **500:** Items List Items Live Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/v2/collections/580e63fc8c9a982ac9b8b745/items/live \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "items": [
    {
      "id": "62b720ef280c7a7a3be8cabe",
      "lastPublished": "2022-06-30T13:35:20.878Z",
      "lastUpdated": "2022-06-25T14:51:27.809Z",
      "createdOn": "2022-06-25T14:51:27.809Z",
      "fieldData": {
        "name": "Senior Data Analyst",
        "slug": "senior-data-analyst",
        "url": "https://boards.greenhouse.io/webflow/jobs/26567701",
        "department": "Data"
      },
      "cmsLocaleId": "66f6e966c9e1dc700a857ca3",
      "isArchived": false,
      "isDraft": false
    },
    {
      "id": "62c880ef281c7b7b4cf9dabc",
      "lastPublished": "2023-04-15T10:25:18.123Z",
      "lastUpdated": "2023-04-10T11:45:30.567Z",
      "createdOn": "2023-04-10T11:45:30.567Z",
      "fieldData": {
        "name": "Product Manager",
        "slug": "product-manager",
        "url": "https://boards.greenhouse.io/webflow/jobs/31234567",
        "department": "Product"
      },
      "cmsLocaleId": "66f6e966c9e1dc700a857ca3",
      "isArchived": false,
      "isDraft": false
    }
  ],
  "pagination": {
    "limit": 25,
    "offset": 0,
    "total": 2
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/live-items/list-items-live](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-items/live-items/list-items-live)*