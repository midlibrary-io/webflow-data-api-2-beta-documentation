# Create Collection Field

```
POST https://api.webflow.com/beta/collections/:collection_id/fields
```

Create a custom field in a collection.
Slugs must be all lowercase letters without spaces.
If you pass a string with uppercase letters and/or spaces to the “Slug” property, Webflow will
convert the slug to lowercase and replace spaces with ”-.”
This endpoint does not currently support bulk creation.
**Required Scope:** `cms:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `type` | enum | No | Choose these appropriate field type for your collection data (Values: Color, DateTime, Email, File, Image, Link, MultiImage, Number, Phone, PlainText, RichText, Switch, VideoLink) |
| `displayName` | string | No | The name of a field |
| `id` | string | No | Unique identifier for a Field |
| `isEditable` | boolean | No | Define whether the field is editable |
| `isRequired` | boolean | No | define whether a field is required in a collection |
| `helpText` | string | No | Additional text to help anyone filling out this field |
| `type` | "Option" | No | TheOption field type |
| `displayName` | string | No | The name of a field |
| `metadata` | object | No | The metadata for the Option field. |
| `metadata.options` | list of objects | No | The option values for the Option field. |
| `metadata.options.name` | string | No | The name of the option |
| `metadata.options.id` | string | No | The unique identifier of the option |
| `id` | string | No | Unique identifier for a Field |
| `isEditable` | boolean | No | Define whether the field is editable |
| `isRequired` | boolean | No | define whether a field is required in a collection |
| `helpText` | string | No | Additional text to help anyone filling out this field |
| `type` | enum | No | Choose these appropriate field type for your collection data (Values: MultiReference, Reference) |
| `displayName` | string | No | The name of a field |
| `metadata` | object | No | The collectionId for the referenced collection. Only applicable for Reference and MultiReference fields. |
| `metadata.collectionId` | string | No | The unique identifier of the collection |
| `id` | string | No | Unique identifier for a Field |
| `isEditable` | boolean | No | Define whether the field is editable |
| `isRequired` | boolean | No | define whether a field is required in a collection |
| `helpText` | string | No | Additional text to help anyone filling out this field |




## Errors

* **400:** Fields Create Request Bad Request Error
* **401:** Fields Create Request Unauthorized Error
* **404:** Fields Create Request Not Found Error
* **409:** Fields Create Request Conflict Error
* **429:** Fields Create Request Too Many Requests Error
* **500:** Fields Create Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/fields \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "isRequired": false,
  "type": "RichText",
  "displayName": "Post Body",
  "helpText": "Add the body of your post here"
}'
```

### Example Response (200 StaticField)

```json
{
  "id": "562ac0395358780a1f5e6fbc",
  "isEditable": true,
  "isRequired": false,
  "type": "RichText",
  "displayName": "Post Body",
  "helpText": "Add the body of your post here"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-fields/create](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-fields/create)*