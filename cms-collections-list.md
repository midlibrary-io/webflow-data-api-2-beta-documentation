# List Collections

```
GET https://api.webflow.com/beta/sites/:site_id/collections
```

List of all Collections within a Site.
**Required Scope:** `cms:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `collections` | list of objects | No | An array of Collections |
| `collections.id` | string | No | Unique identifier for a Collection |
| `collections.displayName` | string | No | Name given to the Collection |
| `collections.singularName` | string | No | The name of one Item in Collection (e.g. ”Blog Post” if the Collection is called “Blog Posts”) |
| `collections.slug` | string | No | Slug of Collection in Site URL structure |
| `collections.createdOn` | datetime | No | The date the collection was created |
| `collections.lastUpdated` | datetime | No | The date the collection was last updated |




## Errors

* **400:** Collections List Request Bad Request Error
* **401:** Collections List Request Unauthorized Error
* **404:** Collections List Request Not Found Error
* **429:** Collections List Request Too Many Requests Error
* **500:** Collections List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/collections \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "collections": [
    {
      "id": "63692ab61fb2852f582ba8f5",
      "displayName": "Products",
      "singularName": "Product",
      "slug": "product",
      "createdOn": "2019-06-12T13:35:14Z",
      "lastUpdated": "2022-11-17T15:08:50Z"
    },
    {
      "id": "63692ab61fb2856e6a2ba8f6",
      "displayName": "Categories",
      "singularName": "Category",
      "slug": "category",
      "createdOn": "2019-06-12T13:35:14Z",
      "lastUpdated": "2022-11-17T15:08:50Z"
    },
    {
      "id": "63692ab61fb285a8562ba8f4",
      "displayName": "SKUs",
      "singularName": "SKU",
      "slug": "sku",
      "createdOn": "2019-06-12T13:35:14Z",
      "lastUpdated": "2022-11-17T15:08:50Z"
    }
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collections/list](https://developers.webflow.com/v2.0.0-beta/reference/cms/collections/list)*