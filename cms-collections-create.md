# Create Collection

```
POST https://api.webflow.com/beta/sites/:site_id/collections
```

Create a Collection for a site.
**Required Scope:** `cms:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | Unique identifier for a Collection |
| `displayName` | string | No | Name given to the Collection |
| `singularName` | string | No | The name of one Item in Collection (e.g. ”Blog Post” if the Collection is called “Blog Posts”) |
| `fields` | list of objects | No | The list of fields in the Collection |
| `fields.id` | string | No | Unique identifier for a Field |
| `fields.isRequired` | boolean | No | define whether a field is required in a collection |
| `fields.type` | enum | No | Choose these appropriate field type for your collection data (Values: Color, DateTime, Email, ExtFileRef, File, Image, Link, MultiImage, MultiReference, Number, Option, Phone, PlainText, Reference, RichText, Switch, VideoLink) |
| `fields.displayName` | string | No | The name of a field |
| `fields.isEditable` | boolean | No | Define whether the field is editable |
| `fields.slug` | string | No | Slug of Field in Site URL structure. Slugs should be all lowercase with no spaces. Any spaces will be converted to ”-.” |
| `fields.helpText` | string | No | Additional text to help anyone filling out this field |
| `slug` | string | No | Slug of Collection in Site URL structure |
| `createdOn` | datetime | No | The date the collection was created |
| `lastUpdated` | datetime | No | The date the collection was last updated |




## Errors

* **400:** Collections Create Request Bad Request Error
* **401:** Collections Create Request Unauthorized Error
* **404:** Collections Create Request Not Found Error
* **409:** Collections Create Request Conflict Error
* **429:** Collections Create Request Too Many Requests Error
* **500:** Collections Create Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/collections \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "displayName": "Blog Posts",
  "singularName": "Blog Post",
  "slug": "posts",
  "fields": [
    {
      "isRequired": true,
      "type": "PlainText",
      "displayName": "Title",
      "helpText": "The title of the blog post"
    },
    {
      "isRequired": true,
      "type": "RichText",
      "displayName": "Content",
      "helpText": "The content of the blog post"
    },
    {
      "isRequired": true,
      "type": "Reference",
      "displayName": "Author",
      "helpText": "The author of the blog post",
      "metadata": {
        "collectionId": "23cc2d952d4e4631ffd4345d2743db4e"
      }
    }
  ]
}'
```

### Example Response (200 Successful)

```json
{
  "id": "562ac0395358780a1f5e6fbd",
  "displayName": "Blog Posts",
  "singularName": "Blog Post",
  "fields": [
    {
      "id": "id",
      "isRequired": true,
      "type": "PlainText",
      "displayName": "Title",
      "isEditable": true,
      "slug": "title",
      "helpText": "The title of the blog post"
    },
    {
      "id": "id",
      "isRequired": true,
      "type": "RichText",
      "displayName": "Content",
      "isEditable": true,
      "slug": "content",
      "helpText": "The content of the blog post"
    },
    {
      "id": "id",
      "isRequired": true,
      "type": "Reference",
      "displayName": "Author",
      "isEditable": true,
      "slug": "author",
      "helpText": "The author of the blog post"
    }
  ],
  "slug": "posts",
  "createdOn": "2016-10-24T19:41:48Z",
  "lastUpdated": "2016-10-24T19:42:38Z"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collections/create](https://developers.webflow.com/v2.0.0-beta/reference/cms/collections/create)*