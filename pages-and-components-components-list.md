# List Components

```
GET https://api.webflow.com/beta/sites/:site_id/components
```

List of all components for a site.
**Required Scope:** `components:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `limit` | double | No | Maximum number of records to be returned (max limit: 100) |
| `offset` | double | No | Offset used for pagination if the results have more than limit records |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `components` | list of objects | No | N/A |
| `components.id` | string | No | Unique identifier for the Component |
| `components.name` | string | No | Component Name |
| `components.group` | string | No | The group that the component belongs to |
| `components.description` | string | No | Component Description |
| `components.readonly` | boolean | No | Indicates whether the component is read-only. Components that cannot be updated within this Site are set to readonly. Workspace Libraries are a good example. |
| `pagination` | object | No | Pagination object |
| `pagination.limit` | double | No | The limit used for pagination |
| `pagination.offset` | double | No | The offset used for pagination |
| `pagination.total` | double | No | The total number of records |




## Errors

* **400:** Components List Request Bad Request Error
* **401:** Components List Request Unauthorized Error
* **404:** Components List Request Not Found Error
* **429:** Components List Request Too Many Requests Error
* **500:** Components List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/components \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "components": [
    {
      "id": "6596da6045e56dee495bcbba",
      "name": "Primary Button",
      "group": "Buttons",
      "description": "A default button component that can be used across the site",
      "readonly": true
    },
    {
      "id": "658205daa3e8206a523b5ad4",
      "name": "Secondary Button",
      "group": "Buttons",
      "description": "A secondary button component that can be used across the site",
      "readonly": true
    },
    {
      "id": "6258612d1ee792848f805dcf",
      "name": "Card",
      "readonly": true
    },
    {
      "id": "68a2b1d1ee792848f805dcf",
      "name": "Nav",
      "readonly": true
    }
  ],
  "pagination": {
    "limit": 20,
    "offset": 0,
    "total": 4
  }
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/components/list](https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/components/list)*