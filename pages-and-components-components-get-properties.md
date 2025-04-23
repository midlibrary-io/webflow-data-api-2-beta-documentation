# Get Component Properties

```
GET https://api.webflow.com/beta/sites/:site_id/components/:component_id/properties
```

Get the default property values of a component definition.
**Required Scope:** `components:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |
| `component_id` | string | Yes | Unique identifier for a Component |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `localeId` | string | No | Unique identifier for a specific locale. Applicable, when using localization. |
| `limit` | double | No | Maximum number of records to be returned (max limit: 100) |
| `offset` | double | No | Offset used for pagination if the results have more than limit records |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `componentId` | string | No | Component ID |
| `properties` | list of objects | No | N/A |
| `properties.propertyId` | string | No | The ID of the property. |
| `properties.type` | enum | No | The type of the property. (Values: Plain Text, Rich Text, Alt Text) |
| `properties.label` | string | No | The label of the property in the UI. |
| `properties.text` | object | No | Represents text content within the DOM. It contains both the raw text and its HTML representation. |
| `properties.text.html` | string | No | The HTML content of the text node. |
| `properties.text.text` | string | No | The raw text content of the text node. |
| `pagination` | object | No | Pagination object |
| `pagination.limit` | double | No | The limit used for pagination |
| `pagination.offset` | double | No | The offset used for pagination |
| `pagination.total` | double | No | The total number of records |




## Errors

* **400:** Components Get Properties Request Bad Request Error
* **401:** Components Get Properties Request Unauthorized Error
* **404:** Components Get Properties Request Not Found Error
* **429:** Components Get Properties Request Too Many Requests Error
* **500:** Components Get Properties Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -G https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/components/8505ba55-ef72-629e-f85c-33e4b703d48b/properties \
     -H "Authorization: Bearer <token>" \
     -d localeId=65427cf400e02b306eaa04a0
```

### Example Response (200 Retrieved)

```json
{
  "componentId": "658205daa3e8206a523b5ad4",
  "properties": [
    {
      "propertyId": "a245c12d-995b-55ee-5ec7-aa36a6cad623",
      "type": "Plain Text",
      "label": "Title",
      "text": {
        "text": "The Hitchhiker's Guide to the Galaxy"
      }
    },
    {
      "propertyId": "a245c12d-995b-55ee-5ec7-aa36a6cad627",
      "type": "Rich Text",
      "label": "Content",
      "text": {
        "html": "<div><h3>Don't Panic!</h3><p>Always know where your towel is.</p></div>"
      }
    }
  ],
  "pagination": {
    "limit": 2,
    "offset": 0,
    "total": 2
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/components/get-properties](https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/components/get-properties)*