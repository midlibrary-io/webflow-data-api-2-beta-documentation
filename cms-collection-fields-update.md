# Update Collection Field

```
PATCH https://api.webflow.com/beta/collections/:collection_id/fields/:field_id
```

Update a custom field in a collection.
**Required Scope:** `cms:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |
| `field_id` | string | Yes | Unique identifier for a Field in a collection |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | Unique identifier for a Field |
| `isRequired` | boolean | No | define whether a field is required in a collection |
| `type` | enum | No | Choose these appropriate field type for your collection data (Values: Color, DateTime, Email, ExtFileRef, File, Image, Link, MultiImage, MultiReference, Number, Option, Phone, PlainText, Reference, RichText, Switch, VideoLink) |
| `displayName` | string | No | The name of a field |
| `isEditable` | boolean | No | Define whether the field is editable |
| `slug` | string | No | Slug of Field in Site URL structure. Slugs should be all lowercase with no spaces. Any spaces will be converted to ”-.” |
| `helpText` | string | No | Additional text to help anyone filling out this field |




## Errors

* **400:** Fields Update Request Bad Request Error
* **401:** Fields Update Request Unauthorized Error
* **404:** Fields Update Request Not Found Error
* **429:** Fields Update Request Too Many Requests Error
* **500:** Fields Update Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X PATCH https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/fields/580e63fc8c9a982ac9b8b745 \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "isRequired": false,
  "displayName": "Post Body",
  "helpText": "Add the body of your post here"
}'
```

### Example Response (200 Updated)

```json
{
  "id": "75821f618da60c18383330bcc0ca488b",
  "isRequired": false,
  "type": "RichText",
  "displayName": "Post Body",
  "isEditable": true,
  "slug": "post-body",
  "helpText": "Add the body of your post here"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-fields/update](https://developers.webflow.com/v2.0.0-beta/reference/cms/collection-fields/update)*