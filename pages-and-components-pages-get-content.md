# Get Page Content

```
GET https://api.webflow.com/beta/pages/:page_id/dom
```

Get content from a static page. This includes text nodes, image nodes, select nodes, text input nodes, submit button nodes, and component instances withproperty overrides.
To retrieve the static content of a component instance, use theGet Component Contentendpoint.
**Required Scope:** `pages:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `page_id` | string | Yes | Unique identifier for a Page |




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
| `pageId` | string | No | Page ID |
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
| `lastUpdated` | datetime | No | The date the page dom was most recently updated |




## Errors

* **400:** Pages Get Content Request Bad Request Error
* **401:** Pages Get Content Request Unauthorized Error
* **403:** Pages Get Content Request Forbidden Error
* **404:** Pages Get Content Request Not Found Error
* **429:** Pages Get Content Request Too Many Requests Error
* **500:** Pages Get Content Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -G https://api.webflow.com/beta/pages/63c720f9347c2139b248e552/dom \
     -H "Authorization: Bearer <token>" \
     -d localeId=65427cf400e02b306eaa04a0
```

### Example Response (200 Retrieved)

```json
{
  "pageId": "658205daa3e8206a523b5ad4",
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
      "type": "select",
      "choices": [
        {
          "value": "choice-1",
          "text": "First choice"
        },
        {
          "value": "choice-2",
          "text": "Second choice"
        }
      ],
      "id": "a245c12d-995b-55ee-5ec7-aa36a6cad635",
      "attributes": {
        "key": "value"
      }
    },
    {
      "type": "text-input",
      "id": "a245c12d-995b-55ee-5ec7-aa36a6cad642",
      "placeholder": "Enter something here...",
      "attributes": {
        "key": "value"
      }
    },
    {
      "type": "text",
      "id": "id",
      "text": {},
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
          "label": "Catchphrase",
          "text": {
            "text": "Don't Panic!"
          }
        },
        {
          "propertyId": "a245c12d-995b-55ee-5ec7-aa36a6cad635",
          "type": "Rich Text",
          "label": "Tagline",
          "text": {
            "html": "<div><p>Always know where your towel is.</p></div>"
          }
        }
      ]
    }
  ],
  "pagination": {
    "limit": 4,
    "offset": 0,
    "total": 4
  },
  "lastUpdated": "2016-10-24T19:42:38Z"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/pages/get-content](https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/pages/get-content)*