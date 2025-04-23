# Update Item Inventory

```
PATCH https://api.webflow.com/beta/collections/:collection_id/items/:item_id/inventory
```

Updates the current inventory levels for a particular SKU item.
Updates may be given in one or two methods, absolutely or incrementally.
**Required Scope:** `ecommerce:write`


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

* **400:** Inventory Update Request Bad Request Error
* **401:** Inventory Update Request Unauthorized Error
* **403:** Inventory Update Request Forbidden Error
* **404:** Inventory Update Request Not Found Error
* **409:** Inventory Update Request Conflict Error
* **429:** Inventory Update Request Too Many Requests Error
* **500:** Inventory Update Request Internal Server Error




## Examples

### Request Example (Bash)

```bash
curl -X PATCH https://api.webflow.com/beta/collections/580e63fc8c9a982ac9b8b745/items/580e64008c9a982ac9b8b754/inventory \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "inventoryType": "infinite"
}'
```

### Example Response (200 Updated)

```json
{
  "id": "5bfedb42bab0ad90fa7dad39",
  "quantity": 100,
  "inventoryType": "finite"
}
```


---
*Source: [https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/inventory/update](https://developers.webflow.com/v2.0.0-beta/reference/ecommerce/inventory/update)*