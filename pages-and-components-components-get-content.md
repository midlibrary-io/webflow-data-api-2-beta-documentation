# Get Component Content

```
GET https://api.webflow.com/beta/sites/:site_id/components/:component_id/dom
```

Get static content from a component definition. This includes text nodes, image nodes, select nodes, text input nodes, submit button nodes, and nested component instances.
To retrieve dynamic content set by component properties, use theget component propertiesendpoint.
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
| `nodes` | list of objects | No | N/A |
| `nodes.Text` | N/A | No | N/A |
| `nodes.Image` | N/A | No | N/A |
| `nodes.Component Instance` | N/A | No | N/A |
| `nodes.Text Input` | N/A | No | N/A |
| `nodes.Select` | N/A | No | N/A |
| `nodes.Submit Button` | N/A | No | N/A |
| `nodes.Search Button` | N/A | No | N/A |
| `pagination` | object | No | Pagination object |
| `pagination.limit` | double | No | The limit used for pagination |
| `pagination.offset` | double | No | The offset used for pagination |
| `pagination.total` | double | No | The total number of records |




## Errors

* **400:** Components Get Content Request Bad Request Error
* **401:** Components Get Content Request Unauthorized Error
* **404:** Components Get Content Request Not Found Error
* **429:** Components Get Content Request Too Many Requests Error
* **500:** Components Get Content Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -G https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/components/8505ba55-ef72-629e-f85c-33e4b703d48b/dom \
     -H "Authorization: Bearer <token>" \
     -d localeId=65427cf400e02b306eaa04a0
```

### Example Response (200 Retrieved)

```json
{
  "componentId": "69118560-d0bc-15fc-bbf8-b8fe5f6535b5",
  "nodes": [
    {
      "type": "text",
      "id": "a245c12d-995b-55ee-5ec7-aa36a6cad623",
      "text": {
        "html": "<h1>The Hitchhiker's Guide to the Galaxy</h1>",
        "text": "The Hitchhiker's Guide to the Galaxy"
      },
      "attributes": {
        "key": "value"
      }
    },
    {
      "type": "text",
      "id": "a245c12d-995b-55ee-5ec7-aa36a6cad627",
      "text": {
        "html": "<div><h3>Don't Panic!</h3><p>Always know where your towel is.</p></div>"
      },
      "attributes": {
        "number": "forty two"
      }
    },
    {
      "type": "image",
      "id": "a245c12d-995b-55ee-5ec7-aa36a6cad629",
      "image": {
        "alt": "Marvin, the Paranoid Android",
        "assetId": "659595234426a9fcbad57043"
      },
      "attributes": {
        "key": "value"
      }
    },
    {
      "type": "text-input",
      "id": "6e468d51-8942-f7be-34cc-347b0e24e118",
      "placeholder": "Search…",
      "attributes": {
        "key": "value"
      }
    },
    {
      "type": "select",
      "choices": [
        {
          "value": "Magrathea",
          "text": "Magrathea"
        },
        {
          "value": "mostly-harmless",
          "text": "Earth"
        },
        {
          "value": "Vogsphere",
          "text": "Vogsphere"
        }
      ],
      "id": "82cdcd0b-b9c7-0ddc-0519-bc1fa02de26e",
      "attributes": {
        "key": "value"
      }
    },
    {
      "type": "submit-button",
      "id": "9fa3a9c4-87d4-19b0-95f7-1b0b099f82ab",
      "value": "Subscribe",
      "waitingText": "Please wait...",
      "attributes": {
        "key": "value"
      }
    },
    {
      "type": "component-instance",
      "componentId": "6258612d1ee792848f805dcf",
      "id": "a245c12d-995b-55ee-5ec7-aa36a6cad631",
      "propertyOverrides": [
        {
          "propertyId": "a245c12d-995b-55ee-5ec7-aa36a6cad633",
          "type": "Plain Text",
          "text": {
            "text": "Don't Panic!"
          }
        },
        {
          "propertyId": "a245c12d-995b-55ee-5ec7-aa36a6cad635",
          "type": "Rich Text",
          "text": {
            "html": "<div><p>Always know where your towel is.</p></div>"
          }
        }
      ]
    }
  ],
  "pagination": {
    "limit": 7,
    "offset": 0,
    "total": 7
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/components/get-content](https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/components/get-content)*