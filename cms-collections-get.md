# Get Collection Details

```
GET https://api.webflow.com/beta/collections/:collection_id
```

Get the full details of a collection from its ID.
**Required Scope:** `cms:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |




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

* **400:** Collections Get Request Bad Request Error
* **401:** Collections Get Request Unauthorized Error
* **404:** Collections Get Request Not Found Error
* **429:** Collections Get Request Too Many Requests Error
* **500:** Collections Get Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745 \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "id": "580e63fc8c9a982ac9b8b745",
  "displayName": "Blog Posts",
  "singularName": "Blog Post",
  "fields": [
    {
      "id": "23cc2d952d4e4631ffd4345d2743db4e",
      "isRequired": true,
      "type": "PlainText",
      "displayName": "Name",
      "isEditable": true,
      "slug": "name"
    }
  ],
  "slug": "post",
  "createdOn": "2016-10-24T19:41:48Z",
  "lastUpdated": "2016-10-24T19:42:38Z"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collections/get](https://developers.webflow.com/v2.0.0-beta/reference/cms/collections/get)*