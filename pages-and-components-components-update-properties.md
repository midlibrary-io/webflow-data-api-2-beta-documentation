# Update Component Properties

```
POST https://api.webflow.com/beta/sites/:site_id/components/:component_id/properties
```

Update the default property values of a component definition in a specificed locale.
Before making updates, use theget component propertiesendpoint to identify properties that can be updated in a secondary locale.
**Required Scope:** `components:write`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `site_id` | string | Yes | Unique identifier for a Site |
| `component_id` | string | Yes | Unique identifier for a Component |




## Query parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `localeId` | string | No | Unique identifier for a specific locale. Applicable, when using localization. |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `errors` | list of strings | No | A list of error messages, if any. |




## Errors

* **400:** Components Update Properties Request Bad Request Error
* **401:** Components Update Properties Request Unauthorized Error
* **404:** Components Update Properties Request Not Found Error
* **429:** Components Update Properties Request Too Many Requests Error
* **500:** Components Update Properties Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X POST "https://api.webflow.com/beta/sites/580e63e98c9a982ac9b8b741/components/8505ba55-ef72-629e-f85c-33e4b703d48b/properties?localeId=65427cf400e02b306eaa04a0" \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "properties": [
    {
      "propertyId": "a245c12d-995b-55ee-5ec7-aa36a6cad623",
      "text": "The Hitchhiker’s Guide to the Galaxy"
    },
    {
      "propertyId": "a245c12d-995b-55ee-5ec7-aa36a6cad627",
      "text": "<div><h3>Dont Panic!</h3><p>Always know where your towel is.</p></div>"
    }
  ]
}'
```

### Example Response (200 Successful)

```json
{
  "errors": [
    "errors"
  ]
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/components/update-properties](https://developers.webflow.com/v2.0.0-beta/reference/pages-and-components/components/update-properties)*