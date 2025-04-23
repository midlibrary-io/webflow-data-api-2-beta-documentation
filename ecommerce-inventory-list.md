# List Inventory

```
GET https://api.webflow.com/beta/collections/:collection_id/items/:item_id/inventory
```

List the current inventory levels for a particular SKU item.
**Required Scope:** `ecommerce:read`


## Path parameters

| Name | Type | Required | Description |
|---|---|---|---|
| `collection_id` | string | Yes | Unique identifier for a Collection |
| `item_id` | string | Yes | Unique identifier for an Item |




## Response

_Request was successful_

### Response Body

| Name | Type | Optional | Description |
|---|---|---|---|
| `id` | string | No | Unique identifier for a SKU item |
| `quantity` | double | No | Total quantity of items remaining in inventory (if inventoryType is finite) |
| `inventoryType` | enum | No | infinite or finite (Values: infinite, finite) |




## Errors

* **400:** Inventory List Request Bad Request Error
* **401:** Inventory List Request Unauthorized Error
* **403:** Inventory List Request Forbidden Error
* **404:** Inventory List Request Not Found Error
* **409:** Inventory List Request Conflict Error
* **429:** Inventory List Request Too Many Requests Error
* **500:** Inventory List Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/items/580e64008c9a982ac9b8b754/inventory \
     -H "Authorization: Bearer <token>"
```

### Example Response (200 Retrieved)

```json
{
  "id": "5bfedb42bab0ad90fa7dad39",
  "quantity": 100,
  "inventoryType": "finite"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/inventory/list](https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/inventory/list)*